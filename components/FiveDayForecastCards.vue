<template>
  <section class="forecast d-flex" elevation="0" v-if="forecastData">
    <v-card class="forecast-card" elevation="0" mb-4>
      <v-container>
        <v-row no-gutters>
          <v-col cols="6">
            <h2 class="forecast-card__title">5-Day Forecast</h2>
          </v-col>
          <v-col
            cols="12"
            v-for="(data, index) in fiveDayData.slice(0, 3)"
            :key="index"
          >
            <v-row no-gutters>
              <v-col cols="4">
                <p class="forecast-card__day">
                  {{ $moment(data.dt_txt).format("dddd") }}
                </p>
              </v-col>
              <v-col cols="4" class="forecast-card__image">
                <img
                  :src="`https://openweathermap.org/img/wn/${data.weather[0].icon}.png`"
                  alt=""
                />
              </v-col>
              <v-col cols="4">
                <div class="forecast-card__temperature">
                  <p class="forecast-card__range">
                    {{ Math.round(data.main.temp_max - 273.15) }}&deg;c
                  </p>
                  <p class="forecast-card__range">
                    {{ Math.round(data.main.temp_min - 273.15) }}&deg;c
                  </p>
                </div>
              </v-col>
            </v-row>
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
          <v-col
            cols="12"
            v-for="(data, index) in fiveDayData.slice(3, 5)"
            :key="index"
          >
            <v-row no-gutters>
              <v-col cols="4">
                <p class="forecast-card__day">
                  {{ $moment(data.dt_txt).format("dddd") }}
                </p>
              </v-col>
              <v-col cols="4" class="forecast-card__image">
                <img
                  :src="`https://openweathermap.org/img/wn/${data.weather[0].icon}.png`"
                  alt=""
                />
              </v-col>
              <v-col cols="4">
                <div class="forecast-card__temperature">
                  <p class="forecast-card__range">
                    {{ Math.round(data.main.temp_max - 273.15) }}&deg;c
                  </p>
                  <p class="forecast-card__range">
                    {{ Math.round(data.main.temp_min - 273.15) }}&deg;c
                  </p>
                </div>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </section>
</template>

<script>
export default {
  computed: {
    forecastData() {
      return this.$store.getters.getForecastData;
    },
    fiveDayData() {
      const arr = this.forecastData.list;
      const result = [];

      for (let i = 0; i < arr.length; i += 8) {
        result.push(arr[i]);
      }

      return result;
    },
  },
};
</script>

<style lang="scss" scoped>
.forecast {
  margin-left: auto;
  margin-right: auto;
}
.forecast-card {
  background: #0d3a8a !important;
  width: 455px;
  border-radius: 20px;
  margin: 15px;
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

  &__image {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__temperature {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }

  &__range {
    font-family: Alegreya Sans;
    font-size: 10px;
    font-weight: 500;
    line-height: 22px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
    margin-right: 13px;
  }

  p {
    margin-bottom: 0;
    line-height: 50px;
  }
}
.d-flex {
  justify-content: space-between;
}
</style>
