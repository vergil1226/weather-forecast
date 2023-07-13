<template>
  <!-- only have to do a 3 hr forecast so stop after 3 hourly / forecast section here in doc-->
  <section class="today">
    <v-card class="today__card" elevation="0">
      <v-container>
        <v-row no-gutters>
          <v-col cols="12">
            <div class="d-flex">
              <h2 class="today-card__title">Today</h2>
              <p class="today-card-date">Mar, 9</p>
            </div>
          <div class="d-flex">
            <p class="today-card-degrees">29&deg;C</p>
            <p class="today-card-degrees">26&deg;C</p>
            <p class="today-card-degrees">24&deg;C</p>
          </div>
          <div class="d-flex">
            <img src="/TodaySunCloud.png" alt="" />
            <img src="/TodaySunCloud.png" alt="" />
            <img src="/TodaySunCloud.png" alt="" />
          </div>
          <div class="d-flex">
            <p class="today-card__time">NOW</p>
            <p class="today-card__time">12PM</p>
            <p class="today-card__time">1PM</p>
          </div>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </section>
</template>

<script>
import FiveDayForecastCards from './FiveDayForecastCards.vue';
export default {
  data() {
    return {
      forecast: {},
    };
  },
  methods: {
    // const date1 = '2023-07-12';
    // const date2 = '2023-07-12';
    // const format = 'YYYY-MM-DD';
    // const isSameDate = moment(date1, format).isSame(moment(date2, format));
    // console.log(isSameDate);
  },
  computed() {},
};
</script>

<style lang="scss" scoped>
.today__card {
  background: radial-gradient(
        77.25% 77.25% at 69.89% 22.75%,
        #5096ff 0%,
        #0044ab 100%
      )
      /* warning: gradient uses a rotation that is not supported by CSS and may not behave as expected */,
    linear-gradient(0deg, #001026, #001026);
  max-width: 940px;
  border-radius: 20px;
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
}
.d-flex {
  flex-direction: space-between;
}
</style>