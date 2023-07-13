<template>
  <!-- only have to do a 3 hr forecast so stop after 3 hourly / forecast section here in doc-->
  <section class="today">
    <v-card class="today-card" elevation="0">
      <v-container>
        <v-row>
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
              <img src="/TodaySunCloud.png" alt="">
              <img src="/TodaySunCloud.png" alt="">
              <img src="/TodaySunCloud.png" alt="">
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
export default {
  data() {
    return {
      forecast: {
    
      }
    }
  },
  methods: {
    // const date1 = '2023-07-12';
    // const date2 = '2023-07-12';
    // const format = 'YYYY-MM-DD';
    // const isSameDate = moment(date1, format).isSame(moment(date2, format));
    // console.log(isSameDate);
  },
  computed() {

  },
};
</script>

<style lang="scss" scoped>
.today{
  max-width: 940px;
  background-color: #001026;
}
.today-card{
  &__title{
    font-family: SF Pro Display;
    font-size: 20px;
    font-weight: 700;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    color: #FFFFFF;
  }
  &__date{
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: right;
    color: #FFFFFF;
  }
  &__degrees{
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: left;
    color: #FFFFFF;
  }
  &__time{
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 500;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
}
</style>