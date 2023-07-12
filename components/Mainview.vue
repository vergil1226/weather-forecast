<template>
  <div class="mainview-weather">
    <v-speed-dial
      direction="top"
      transition="slide-y-reverse"
      absolute
      right
      top
    >
      <v-btn elevation="0"><v-icon>mdi-refresh</v-icon></v-btn>
      <img src="/Suncloud.png" alt="" />
      <h1 class="mainview-weather__title">Tarpon Springs</h1>
      <p class="mainview-weather__degree">30&deg;</p>
      <p class="mainview-weather__description">Mostly Sunny</p>
      <p class="mainview-weather__range">High: 34&deg; Low: 28&deg;</p>
    </v-speed-dial>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.mainview-weather{
  &__title{
    font-family: SF Pro Display;
    font-size: 31px;
    font-weight: 400;
    line-height: 37px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
  &__degree{
    font-family: SF Pro Display;
    font-size: 64px;
    font-weight: 600;
    line-height: 76px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
  &__description{
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
  &__range{
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
}
</style>