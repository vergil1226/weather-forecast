<template>
  <section class="mainview-weather" elevation="0">
    <!-- check sass variables for vuetify components -->
    <vue-custom-scrollbar
      class="scroll-area"
      :settings="settings"
      @ps-scroll-y="scrollHanle"
    >
      <v-container>
        <v-btn fab class="btn-refresh" @click="onRefresh">
          <v-icon>mdi-refresh</v-icon>
        </v-btn>
        <v-row v-if="receivedData">
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
              </v-speed-dial>
            </v-card>
            <div class="mainview-weather__content">
              <img
                :src="getImageSrc"
                class="mainview-weather__graphic"
                alt=""
              />
              <h1 class="mainview-weather__title">{{ receivedData.name }}</h1>
              <p class="mainview-weather__degree">
                {{ Math.round(receivedData.main.temp - 273.15) }}&deg;
              </p>
              <p class="mainview-weather__description">
                {{ receivedData.weather[0].description }}
              </p>
              <p class="mainview-weather__range">
                High: {{ Math.round(receivedData.main.temp_max - 273.15) }}&deg;
                Low: {{ Math.round(receivedData.main.temp_min - 273.15) }}&deg;
              </p>
            </div>
          </v-col>
          <v-col cols="12">
            <TodayCard />
          </v-col>
          <v-col cols="12" class="d-flex">
            <FiveDayForecastCards />
          </v-col>
        </v-row>
      </v-container>
    </vue-custom-scrollbar>
  </section>
</template>

<script>
import TodayCard from "./TodayCard.vue";
import FiveDayForecastCards from "./FiveDayForecastCards.vue";
import vueCustomScrollbar from "vue-custom-scrollbar";
import "vue-custom-scrollbar/dist/vueScrollbar.css";
export default {
  components: { TodayCard, FiveDayForecastCards, vueCustomScrollbar },
  data() {
    return {
      settings: {
        suppressScrollY: false,
        suppressScrollX: false,
        wheelPropagation: false,
      },
    };
  },
  methods: {
    scrollHanle(evt) {
      // console.log(evt);
    },
    async onRefresh() {
      const apiKey = "e0c71a38f202d6ce20e080c1f164cf2e";
      let updatedList = [];
      let updatedForecastList = [];

      for (let i = this.recentList.length - 1; i >= 0; i--) {
        let resp = null;
        await this.$axios
          .$get(
            `https://api.openweathermap.org/data/2.5/weather?q=${this.recentList[i].name}&appid=${apiKey}`
          )
          .then((response) => {
            resp = response;
            updatedList.push(response);
          })
          .catch((error) => {
            console.error(error);
          });

        if (resp != null) {
          await this.$axios
            .$get(
              `https://api.openweathermap.org/data/2.5/forecast?lat=${resp.coord.lat}&lon=${resp.coord.lon}&appid=${apiKey}`
            )
            .then((res) => {
              updatedForecastList.push(res);
            })
            .catch((err) => {
              console.log(err);
            });
        }
      }

      this.$store.dispatch("refresh", { updatedList, updatedForecastList });
    },
  },
  computed: {
    receivedData() {
      return this.$store.getters.getSharedData;
    },
    recentList() {
      return this.$store.getters.getRecentList;
    },
    getImageSrc() {
      return `https://openweathermap.org/img/wn/${this.receivedData.weather[0].icon}@4x.png`;
    },
  },
  mounted() {
    setInterval(() => {
      this.onRefresh();
    }, 5 * 60 * 1000);
  },
};
</script>

<style lang="scss" scoped>
.mainview-weather {
  background: linear-gradient(135deg, #08244f 0%, #134cb5 47.38%, #0b42ab 100%);
  width: calc(100vw - 375px);
  height: 100vh;
  box-sizing: border-box;
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
    text-transform: capitalize;
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
    width: 200px;
    height: 200px;
    visibility: visible !important;
  }
}
.scroll-area {
  position: relative;
  margin: auto;
  height: 100vh;
}

.btn-refresh {
  position: absolute;
  top: 27px;
  right: 45px;
  border-radius: 54px;
  background-color: #15488a !important;
  width: 54px;
  height: 54px;
  border: 1px solid #377ce5;
  box-shadow: none;
}
</style>
