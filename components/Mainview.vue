<template>
  <section class="mainview-weather" elevation="0">
    <!-- check sass variables for vuetify components -->
    <v-container>
      <v-row>
        <v-col cols="12">
          <v-card elevation="0">
            <v-speed-dial
              direction="top"
              transition="slide-y-reverse"
              absolute
              right
              top
              class="mainview-weather__refresh"
            >
              <v-card-text style="height: 100px; position: relative">
                <v-fab-transition>
                  <v-btn
                    v-show="!hidden"
                    color="white"
                    dark
                    absolute
                    top
                    right
                    float
                    fab
                    elevation="0"
                    v-icon="mdi - refresh"
                  >
                  </v-btn>
                </v-fab-transition>
              </v-card-text>
            </v-speed-dial>
          </v-card>
          <div class="mainview-weather__content">
            <img src="/Suncloud.png" class="mainview-weather__graphic" alt="" />
            <h1 class="mainview-weather__title">Tarpon Springs</h1>
            <p class="mainview-weather__degree">30&deg;</p>
            <p class="mainview-weather__description">Mostly Sunny</p>
            <p class="mainview-weather__range">High: 34&deg; Low: 28&deg;</p>
          </div>
        </v-col>
        <v-col cols="12">
          <TodayCard />
        </v-col>
        <v-col cols="12">
          <FiveDayForecastCards />
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
import TodayCard from "./TodayCard.vue";
import FiveDayForecastCards from "./FiveDayForecastCards.vue";
export default {
  components: { TodayCard, FiveDayForecastCards },
};
</script>

<style lang="scss" scoped>
.mainview-weather {
  background: radial-gradient(
        77.25% 77.25% at 69.89% 22.75%,
        #5096ff 0%,
        #0044ab 100%
      )
      /* warning: gradient uses a rotation that is not supported by CSS and may not behave as expected */,
    linear-gradient(0deg, #15488a, #15488a);
  width: 1001px;
  height: 999px;
  &__title {
    font-family: SF Pro Display;
    font-size: 31px;
    font-weight: 400;
    line-height: 37px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
  }
  &__degree {
    font-family: SF Pro Display;
    font-size: 64px;
    font-weight: 600;
    line-height: 76px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
  }
  &__description {
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
  }
  &__range {
    font-family: SF Pro Display;
    font-size: 18px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
  }
  &__graphic {
    display: flex;
    justify-content: center;
    margin: auto;
  }
}
</style>