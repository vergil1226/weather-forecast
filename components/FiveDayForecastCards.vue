<template>
  <div class="d-flex">
    <v-card class="forecast-card" elevation="0">
      <v-container>
        <v-row>
          <v-col cols="6">
            <h2 class="forecast-card__title">5-Day Forecast</h2>
            <p class="forecast-card-day">Monday</p>
            <img src="/RainDrops.png" alt="" />
            <p class="forecast-card__range">13&deg;C</p>
            <p class="forecast-card__range">10&deg;C</p>
          </v-col>
          <v-col cols="12">
            <p class="forecast-card-day">Tuesday</p>
            <img src="/ThunderLightening.png" alt="" />
            <p class="forecast-card__range">17&deg;C</p>
            <p class="forecast-card__range">12&deg;C</p>
          </v-col>
          <v-col cols="12">
            <p class="forecast-card-day">Wednesday</p>
            <img src="/SunCloudRain.png" alt="" />
            <p class="forecast-card__range">21&deg;C</p>
            <p class="forecast-card__range">18&deg;C</p>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
    <v-card class="forecast-card" elevation="0">
      <v-container>
        <v-row>
          <v-col cols="6">
            <h2 class="forecast-card__title">5-Day Forecast</h2>
            <p class="forecast-card-day">Monday</p>
            <img src="/RainDrops.png" alt="" />
            <p class="forecast-card__range">13&deg;C</p>
            <p class="forecast-card__range">10&deg;C</p>
          </v-col>
          <v-col cols="12">
            <p class="forecast-card-day">Tuesday</p>
            <img src="/ThunderLightening.png" alt="" />
            <p class="forecast-card__range">17&deg;C</p>
            <p class="forecast-card__range">12&deg;C</p>
          </v-col>
          <v-col cols="12">
            <p class="forecast-card-day">Wednesday</p>
            <img src="/SunCloudRain.png" alt="" />
            <p class="forecast-card__range">21&deg;C</p>
            <p class="forecast-card__range">18&deg;C</p>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.forecast-card {
  background-color: #5096ff;
  width: 455px;
  height: 256px;
  &__title {
    font-family: SF Pro Display;
    font-size: 20px;
    font-weight: 700;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__day {
    font-family: Alegreya Sans;
    font-size: 18px;
    font-weight: 700;
    line-height: 22px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__range {
    font-family: Alegreya Sans;
    font-size: 18px;
    font-weight: 500;
    line-height: 22px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
    margin-right: 13px;
  }
}
</style>