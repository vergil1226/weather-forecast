<template>
  <div>
    <v-card class="forecast-card" elevation="0" color="#5096FF">
      <h3 class="forecast-card__title">5-Day Forecast</h3>
      <div class="d-flex">
        <ol class="forecast-card-list">
          <li class="forecast-card-list__items">Monday</li>
          <li class="forecast-card-list__items">Tuesday</li>
          <li class="forecast-card-list__items">Wednesday</li>
        </ol>
      </div>
      <div>
        <v-icon>mdi-google-circles-extended</v-icon>
        <v-icon>mdi-weather-lightning</v-icon>
        <v-icon>mdi-weather-partly-rainy</v-icon>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
</style>