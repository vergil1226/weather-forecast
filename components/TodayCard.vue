<template>
  <!-- only have to do a 3 hr forecast so stop after 3 hourly / forecast section here in doc-->
  <section class="today" v-if="forecastData">
    <v-card class="today-card" elevation="0">
      <v-container>
        <v-row no-gutters>
          <v-col cols="6">
            <h2 class="today-card__title">Today</h2>
          </v-col>
          <v-col cols="6">
            <p class="today-card__date">{{ $moment().format("MMMM, DD") }}</p>
          </v-col>
          <v-col
            class="today-card__main"
            cols="1.5"
            v-for="(data, index) in forecastData.list.slice(0, 8)"
            :key="index"
          >
            <div class="d-flex">
              <p class="today-card__degrees">
                {{ Math.round(data.main.temp - 273.15) }}&deg;C
              </p>
            </div>
            <div class="d-flex">
              <img
                :src="`https://openweathermap.org/img/wn/${data.weather[0].icon}.png`"
                class="today-card__graphic"
                alt=""
              />
            </div>
            <div class="d-flex">
              <p class="today-card__time">{{ $moment(data.dt_txt).format("h A") }}</p>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </section>
</template>

<script>
export default {
  data() {
    return {
      forecast: {},
    };
  },
  methods: {},
  computed: {
    forecastData() {
      return this.$store.getters.getForecastData;
    },
  },
};
</script>

<style lang="scss" scoped>
.today-card {
  background: #0d3a8a;
  max-width: 940px;
  border-radius: 20px;
  margin-left: auto;
  margin-right: auto;
  &__main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    
    div {
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
  &__title {
    font-family: SF Pro Display;
    font-size: 20px;
    font-weight: 700;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__date {
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: right;
    color: #ffffff;
  }
  &__degrees {
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__time {
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 500;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
  }
  &__graphic {
    height: 50px;
    width: 50px;
    display: flex;
    justify-content: center;
  }
}
.d-flex {
  justify-content: space-between;
}
</style>
