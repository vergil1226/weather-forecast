<template>
  <v-app>
    <sidebar />
    <v-main>
      <Mainview />
      <Nuxt />
    </v-main>
  </v-app>
       
</template>

<script>
import Vue from 'vue'
import VTooltip from 'v-tooltip'
import Sidebar from '../components/Sidebar.vue'
import Mainview from '../components/Mainview.vue'

export default {
  components: { Sidebar, Mainview},
  name: 'IndexPage'
}
</script>
