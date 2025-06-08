<script setup>
import { ref, computed } from 'vue'
import Home from './components/home.vue'
import NotFound from './components/NotFound.vue'
import Profile from './components/Profile.vue'
import illust_Page1 from './illustration/pages/page1.vue'
import illust_Page2 from './illustration/pages/page2.vue'
import illust_Page3 from './illustration/pages/page3.vue'
import illust_Page4 from './illustration/pages/page4.vue'
import illust_Page5 from './illustration/pages/page5.vue'
import illust_Page6 from './illustration/pages/page6.vue'
import illustration from './illustration/illustration.vue'

import Quantum from './quantum/quantum.vue'
import code from './quantum/pages/page1.vue'
import conference from './quantum/pages/page2.vue'

import modeling from './3DCG/3DCG.vue'
import blender from './3DCG/pages/page1.vue'
import maya from './3DCG/pages/page2.vue'


const routes = {
  '/': Home,
  '/profile':Profile,
  '/illust_page1': illust_Page1,
  '/illust_page2': illust_Page2,
  '/illust_page3': illust_Page3,
  '/illust_page4': illust_Page4,
  '/illust_page5': illust_Page5,
  '/illust_page6': illust_Page6,
  '/illustration': illustration,

  '/quantum': Quantum,
  '/quantum_page1': code,
  '/quantum_page2': conference,

  '/3DCG':modeling,
  '/3DCG_page1':blender,
  '/3DCG_page2':maya
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
  <component :is="currentView" />
</template>