<template>
  <!-- only have to do a 3 hr forecast so stop after 3-->
  <div>
    <v-card class="today-card" elevation="0">
      <v-container>
        <v-row>
          <v-col cols="12">
            <div class="d-flex">
              <h2 class="today-card__title">Today</h2>
              <p class="today-card-date">Mar, 9</p>
            </div>
            <div class="d-flex">
              <p class="today-card-degrees">29 C</p>
              <p class="today-card-degrees">26 C</p>
              <p class="today-card-degrees">24 C</p>
            </div>
            <div class="d-flex">
              <img src="/TodaySunCloud.png" alt="">
              <img src="/TodaySunCloud.png" alt="">
              <img src="/TodaySunCloud.png" alt="">
            </div>
            <div class="d-flex">
              <p class="today-card-time">NOW</p>
              <p class="today-card-time">12PM</p>
              <p class="today-card-time">1PM</p>
            </div>
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