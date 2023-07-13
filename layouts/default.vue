<template>
  <v-app dark>
    <Sidebar />
    <v-main>
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
import Vue from 'vue'
import VTooltip from 'v-tooltip'
import Sidebar from '../components/Sidebar.vue'
export default {
  components: { Sidebar },
  name: 'IndexPage'
}

</script>
