<template>
  <!--- set to refresh every 5 minutes use built in js interval in the mounted lifecycle hook - need to update the timeout method-->
  <section class="sidebar" float elevation="0">
    <v-app>
      <v-main>
        <v-card elevation="0">
          <v-navigation-drawer class="app__sidebar" width="375px" permanent>
            <!-- need to add fab -->
            <v-list>
              <v-card class="sidebar__card" elevation="0">
                <v-text-field
                  v-model="searchQuery"
                  loading="isloading"
                  prepend-inner-icon="mdi-map-marker-outline"
                  placeholder="Add Location..."
                  @keyup.enter="searchLocation"
                  class="app__search"
                  rounded
                  hide-details="auto"
                ></v-text-field>
                <!-- <Snackbar /> -->
                <v-snackbar v-model="snackbarShow" :timeout="3000" color="blue" :top="true"
                  >Please input correct location</v-snackbar
                >
                <vue-custom-scrollbar
                  class="scroll-area"
                  :settings="settings"
                  @ps-scroll-y="scrollHanle"
                >
                  <recent-list />
                </vue-custom-scrollbar>
              </v-card>
            </v-list>
          </v-navigation-drawer>
        </v-card>
      </v-main>
    </v-app>
  </section>
</template>

<script>
import RecentList from "./RecentList.vue";
import Snackbar from "./Snackbar.vue";
import vueCustomScrollbar from "vue-custom-scrollbar";
import "vue-custom-scrollbar/dist/vueScrollbar.css";

export default {
  components: {
    RecentList,
    Snackbar,
    vueCustomScrollbar,
  },
  data() {
    return {
      searchQuery: "",
      items: [],
      settings: {
        suppressScrollY: false,
        suppressScrollX: false,
        wheelPropagation: false,
      },
      snackbarShow: false,
    };
  },
  props: {
    width: {
      type: [Number, String],
    },
  },
  methods: {
    async searchLocation() {
      // Here you can perform the search logic for the entered location
      // You can access the entered location via `this.searchQuery`
      const apiKey = "e0c71a38f202d6ce20e080c1f164cf2e"; // Replace with your OpenWeather API key
      const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${this.searchQuery}&appid=${apiKey}`;
      console.log(apiUrl);

      let resp = null;
      await this.$axios
        .$get(apiUrl)
        .then((response) => {
          console.log(response); // Handle the response data here
          this.$store.dispatch("updateSharedData", response);
          resp = response;
          this.searchQuery = "";
        })
        .catch((error) => {
          console.error(error);
          this.snackbarShow = true;
        });

      if (resp != null) {
        await this.$axios
          .$get(
            `https://api.openweathermap.org/data/2.5/forecast?lat=${resp.coord.lat}&lon=${resp.coord.lon}&appid=${apiKey}`
          )
          .then((res) => {
            console.log(res);
            this.$store.dispatch("updateForecastData", res);
          })
          .catch((err) => {
            console.log(err);
          });
      }
    },
    scrollHanle(evt) {
      // console.log(evt);
    },
  },
};
</script>

<style lang="scss" scoped>
.sidebar {
  max-width: 375px;
  height: 100vh;
  &__card {
    padding: 30px 0px 30px 0px;
    background-color: #104084;
  }
}
.scroll-area {
  position: relative;
  margin: auto;
  height: calc(100vh - 145px);
  background-color: #104084;
}
.v-list {
  padding: 0;
}

.app__sidebar {
  background-color: #104084;
}
.app__search {
  margin-right: 16px;
  margin-left: 13px;
  margin-bottom: 27px;
  background: rgba(37, 102, 163, 0.2);
  filter: none;
  border-radius: 10px !important;
  box-shadow: none;
  padding: 10px 0;
  border: 1px solid #377ce5;
}
</style>
