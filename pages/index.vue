<template>
  <v-app>
    <sidebar />
    <v-main>
      <Mainview />
      <TodayCard />
      <FiveDayForecastCards />
      <Nuxt />
    </v-main>
  </v-app>
       
</template>

<script>
import Vue from 'vue'
import VTooltip from 'v-tooltip'
import Sidebar from '../components/Sidebar.vue'
import Mainview from '../components/Mainview.vue'
import TodayCard from '../components/TodayCard.vue'
import FiveDayForecastCards from '../components/FiveDayForecastCards.vue'
export default {
  components: { Sidebar, Mainview, TodayCard, FiveDayForecastCards },
  name: 'IndexPage'
}
</script>
