<template>
  <div>
    <v-speed-dial
      direction="top"
      transition="slide-y-reverse"
      absolute
      right
      top
    >
      <v-btn><v-icon>mdi-refresh</v-icon></v-btn>
    </v-speed-dial>
    <FiveDayForecastCards />
  </div>
</template>

<script>
import FiveDayForecastCards from './FiveDayForecastCards.vue';
export default {};
</script>

<style lang="scss" scoped>
</style>