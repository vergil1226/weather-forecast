<template>
  <section class="forecast d-flex" elevation="0">
    <v-card class="forecast-card" elevation="0" mb-4>
      <v-container>
        <v-row no-gutters>
          <v-col cols="6">
            <h2 class="forecast-card__title">5-Day Forecast</h2>
          </v-col>
          <v-col cols="12">
            <div class="d-flex">
              <p class="forecast-card-day">Monday</p>
              <img src="/RainDrops.png" alt="" />
              <div class="d-flex">
                <p class="forecast-card__range">13&deg;C</p>
                <p class="forecast-card__range">10&deg;C</p>
              </div>
            </div>
          </v-col>
          <v-col cols="12">
            <div class="d-flex">
              <p class="forecast-card-day">Tuesday</p>
              <img src="/ThunderLightening.png" alt="" />
              <div class="d-flex">
                <p class="forecast-card__range">17&deg;C</p>
                <p class="forecast-card__range">12&deg;C</p>
              </div>
            </div>
          </v-col>
          <v-col cols="12">
            <div class="d-flex">
              <p class="forecast-card-day">Wednesday</p>
              <img src="/SunCloudRain.png" alt="" />
              <div class="d-flex">
                <p class="forecast-card__range">21&deg;C</p>
                <p class="forecast-card__range">18&deg;C</p>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
    <!-- use v-for loop to make identical card-->
    <v-card class="forecast-card" elevation="0" mb-4>
      <v-container>
        <v-row no-gutters>
          <v-col cols="6">
            <h2 class="forecast-card__title">5-Day Forecast</h2>
          </v-col>
          <v-col cols="12">
            <div class="d-flex">
              <p class="forecast-card-day">Monday</p>
              <img src="/RainDrops.png" alt="" />
              <div class="d-flex">
                <p class="forecast-card__range">13&deg;C</p>
                <p class="forecast-card__range">10&deg;C</p>
              </div>
            </div>
          </v-col>
          <v-col cols="12">
            <div class="d-flex">
              <p class="forecast-card-day">Tuesday</p>
              <img src="/ThunderLightening.png" alt="" />
              <div class="d-flex">
                <p class="forecast-card__range">17&deg;C</p>
                <p class="forecast-card__range">12&deg;C</p>
              </div>
            </div>
          </v-col>
          <v-col cols="12">
            <div class="d-flex">
              <p class="forecast-card-day">Wednesday</p>
              <img src="/SunCloudRain.png" alt="" />
              <div class="d-flex">
                <p class="forecast-card__range">21&deg;C</p>
                <p class="forecast-card__range">18&deg;C</p>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.forecast-card {
  background: rgb(0,68,171);
  width: 455px;
  border-radius: 20px;
  margin-top: 42px;
  margin-left: 31px;
  &__title {
    font-family: SF Pro Display;
    font-size: 20px;
    font-weight: 700;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
    padding-bottom: 17px;
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
.d-flex {
  justify-content: space-between;
}
</style>