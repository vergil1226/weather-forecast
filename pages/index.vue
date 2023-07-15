<template>
  <v-app>
    <v-main>
        <Mainview />
      <Nuxt />
    </v-main>
  </v-app>
       
</template>

<script>
import Vue from 'vue'
import VTooltip from 'v-tooltip'
import Mainview from '../components/Mainview.vue'

export default {
  components: { Vue, Mainview},
  name: 'IndexPage'
}
</script>
