<script setup>
    import sub1 from "@/assets/img/quantum/spin.jpg";
    import sub2 from "@/assets/img/quantum/comparison.jpg";
    import sub3 from "@/assets/img/quantum/server.jpg";

</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>概要</h1>
            <p>ヨーロッパの量子コンピュータD-WaveとNTT社の量子コンピュータCIMの性能比較を行っている。</p>
            <p>NP困難である巡回セールズマン問題（TSP）を対象として比較している。</p>
            <p>巡回セールズマン問題とは、N個の都市を１回ずつ訪問する場合、最短巡回路長を求める問題である。</p>
            <p>N=10ではすでに組み合わせ数が約20万になってしまうが、量子のアプローチからより解きやすくなる。</p>
        </div>

        <div class="Dwave">
            <h1>D-wave</h1>
            <p>APIを使うとD-wave社の量子コンピュータにアクセスできる。</p>
            <p>自作コードを以下に示す（Python、Jupyter環境）。</p>
            <pre><code>
              import numpy as np

              # ファイル名を指定
              filename = 'distance_matrix_a.txt'

              # テキストファイルから行列を読み込む
              with open(filename, 'r') as file:
                  # ファイルの内容を読み込み、余分な文字を除去してからリスト形式に変換
                  data = file.read().strip().splitlines()
                  data = [list(map(float, filter(lambda x: x.strip(), line.split()))) for line in data]

              # 読み込んだデータをnumpy配列に変換
              Q = np.array(data)

              import numpy as np

              N = 5 # 正解1.5802384136814005

              # 変数を作成
              from pyqubo import Array, Constraint, Placeholder
              x = Array.create('x', shape=(N, N), vartype='BINARY')

              # コスト関数
              cost = 0
              for t in range(N):
                for i in range(N):
                  for j in range(N):
                    cost += Q[i][j]*x[t][i]*x[(t+1)%N][j]


              # 制約条件1：各都市に1回は訪問しなければならない
              constr_1 = 0
              for i in range(N):
                constr_1 += (np.sum(x[i])-1)**2

              # 制約条件2：1度に訪れる都市は1つでなければならない
              constr_2 = 0
              for i in range(N):
                constr_2 += (np.sum(x.T[i])-1)**2


              cost_func = cost + Placeholder('lam')*Constraint(constr_1, label='constr_1')\
                               + Placeholder('lam')*Constraint(constr_2, label='constr_2')
              model = cost_func.compile()


              feed_dict = {'lam': 1} # penalty係数
              qubo, offset = model.to_qubo(feed_dict=feed_dict)

              token = "My-token" # ここにAPIを入力
              endpoint = 'https://cloud.dwavesys.com/sapi/'

              from dwave.system import DWaveSampler, EmbeddingComposite
              dw_sampler = DWaveSampler(solver='Advantage_system6.4', token=token, endpoint=endpoint)     
              sampler = EmbeddingComposite(dw_sampler)    
              sampleset = sampler.sample_qubo(qubo, num_reads=10)
              print(sampleset.record)

              # 制約条件を守っているかどうかの情報を得ることができる
              # decoded_samples = model.decode_sampleset(sampleset=sampleset, feed_dict=feed_dict)
              # for sample in decoded_samples:
              #  print(sample.constraints(only_broken=True))
                          
              # 計算時間を出力
              print(f'全体の時間は{sampleset.info["timing"]}')
                          
              # timing_results = []
              # for _ in range(10): # 実行回数
              #     sampleset = sampler.sample_qubo(qubo, num_reads=1)
              #     timing_results.append(sampleset.info["timing"])
              
              # print("個別な時間は", timing_results)
              
              # qpu_sampling_time + qpu_anneal_time_per_sample + qpu_readout_time_per_sample
              cal_time = sampleset.info["timing"]['qpu_sampling_time'] + sampleset.info["timing"]['qpu_anneal_time_per_sample']\
                          + sampleset.info["timing"]['qpu_readout_time_per_sample']
              print(f'計算にかかった時間は{cal_time}μs')
              
              # 制約条件に合う解をデコードし、巡回長を計算する
              decoded_samples = model.decode_sampleset(sampleset=sampleset, feed_dict=feed_dict)
              
              # 制約条件を満たすすべての解について巡回距離を計算する
              for idx, sample in enumerate(decoded_samples):
                  # 制約条件を破っていない解だけを処理
                  if not sample.constraints(only_broken=True):  # {} の解だけを対象とする
                      order = []
                      for t in range(N):
                          for i in range(N):
                              if sample.sample[f'x[{t}][{i}]'] == 1:
                                  order.append(i)
                                  break
              
                      # 距離を計算
                      total_distance = 0
                      for i in range(len(order)):
                          total_distance += Q[order[i]][order[(i+1) % N]]
              
                      print(f"制約条件を満たす解 {idx + 1}:")
                      print("巡回順:", order)
                      print("巡回距離:", total_distance)

              results = []

              # ペナルティ係数を変更しながら実験
              for lam in np.arange(0.7, 1.4, 0.2):
                  feed_dict = {'lam': lam}
                  qubo, offset = model.to_qubo(feed_dict=feed_dict)

                  for trial in range(10):
                      sampleset = sampler.sample_qubo(qubo, num_reads=1)
                      decoded_samples = model.decode_sampleset(sampleset=sampleset, feed_dict=feed_dict)
                      found_valid_solution = False

                      for idx, sample in enumerate(decoded_samples):
                          if not sample.constraints(only_broken=True):  # 制約条件を満たす解を探す
                              order = [i for t in range(N) for i in range(N) if sample.sample[f'x[{t}][{i}]'] == 1]
                              total_distance = sum(Q[order[i]][order[(i+1) % N]] for i in range(len(order)))

                              results.append({'lambda': lam, 'trial': trial + 1, 'solution_idx': idx + 1, 'distance': total_distance, 'order': order})
                              found_valid_solution = True

                      # 制約を満たす解が1つもない場合の記録
                      if not found_valid_solution:
                          results.append({'lambda': lam, 'trial': trial + 1, 'solution_idx': None, 'distance': None, 'order': None})

              df = pd.DataFrame(results)
              df.to_csv('tsp_dwave_results.csv', index=False)

              print("結果をtsp_dwave_results.csvに保存しました。")
            </code></pre>

            <p>コードの中身は、TSP問題を定式化し、D-waveより解を計算し、計算時間や結果などを記録するものである。</p>
            <p>そして定式化の際にペナルティ係数を決める必要があり、量子コンピュータの性能の良さと関係ある。コードの最後は最良のペナルティ係数を決めるためのものである。</p>

        </div>

        <div class="CIM">
            <h1>CIM</h1>
            <p>NTT社の量子コンピュータCIMはNTT社のサーバに接続必要があり、一般公開されていないためAPIがなく、関連のプログラムコードを載せることが難しい。</p>
            <p>以下は、実験による結果のグラフのみを示す。</p>
            <div class="wrapper">
              <div><img class="subimg" :src="sub1"/><br>スピンの発展（TSP10都市、C言語シミュレーション）</div>
              <div><img class="subimg" :src="sub2"/><br>CIMとDWaveの正答率の比較（Pythonシミュレーション）</div>
              <div><img class="subimg" :src="sub3"/><br>CIMのPythonシミュレーションが研究室のサーバで実行される様子</div>
            </div>
        </div>

    <h1><a href="#/quantum">←Back</a></h1> 
  </div>
</template>

<style scoped>
.CIM {
  text-align: left; /* 明示的に文字は左揃え */
}

.wrapper {
  text-align: center; /* この中の要素を中央寄せ */
  margin: 20px 0;     /* 上下に余白（任意） */
}

.subimg {
  width: 800px;
  height: auto;
  object-fit: contain;
}
.waku{
  display: grid;
}

</style>