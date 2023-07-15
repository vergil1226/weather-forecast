<template>
  <v-app dark class="app">
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
<style lang="scss" scoped>
.app{
  display: flex;
  flex-direction: row;
}
</style>