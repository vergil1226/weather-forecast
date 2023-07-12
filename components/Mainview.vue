<template>
  <div>
    <v-speed-dial
      direction="top"
      transition="slide-y-reverse"
      absolute
      right
      top
    >
      <v-btn elevation="0"><v-icon>mdi-refresh</v-icon></v-btn>
      <img src="/Suncloud.png" alt="">
      <h1 class="weather-card__title">Tarpon Springs</h1>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Sunny</p>
                  <p class="weather-card__degree">30</p>
                  <p class="weather-card__range">High: 34 Low: 28</p>
    </v-speed-dial>
    <TodayCard />
    <FiveDayForecastCards />
  </div>
</template>

<script>
import TodayCard from './TodayCard.vue';
import FiveDayForecastCards from './FiveDayForecastCards.vue';
export default {};
</script>

<style lang="scss" scoped>
</style>