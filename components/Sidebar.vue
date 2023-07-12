<template>
  <v-app>
    <v-card height="999" width="375" elevation="0">
      <v-navigation-drawer class="app__sidebar" color="#104084" dark permanent>
        <v-list>
          <v-card class="app__card">
            <v-text-field
              v-model="searchQuery"
              prepend-inner-icon="mdi-map-marker-outline"
              placeholder="Add Location..."
              class="white-placeholder white-text"
              @keyup.enter="searchLocation"
            >
            </v-text-field>
          </v-card>
          <v-card class="weather-card">
            <h1 class="weather-card__title">Tarpon Springs</h1>
            <p class="weather-card__time">11:22 AM</p>
            <p class="weather-card__description">Mostly Sunny</p>
            <p class="weather-card__degree">30</p>
            <p class="weather-card__range">High: 34 Low: 28</p>
          </v-card>
          <v-list-item v-for="item in items" :key="item.title" link>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-card>
  </v-app>
</template>




<script>
export default {
  data() {
    return {
      searchQuery: "",
    };
  },
  methods: {
    searchLocation() {
      // Here you can perform the search logic for the entered location
      // You can access the entered location via `this.searchQuery`
      console.log("Search query:", this.searchQuery);
    },
  },
};
</script>

<style lang="scss" scoped>
.white-placeholder {
  color: #ffffff;
}
.weather-card{
  &__title{
    font-family: SF Pro Display;
    font-size: 22px;
    font-weight: 500;
    line-height: 26px;
    letter-spacing: 0em;
    text-align: left;
    color: #FFFFFF;
  }
  &__time{
    font-family: SF Pro Display;
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: left;
    color: #FFFFFF;
  }
  &__description{
    font-family: SF Pro Display;
    font-size: 16px;
    font-weight: 500;
    line-height: 19px;
    letter-spacing: 0em;
    text-align: left;
    color: #FFFFFF;
  }
  &__degree{
    font-family: SF Pro Display;
    font-size: 50px;
    font-weight: 500;
    line-height: 60px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
  &__range{
    font-family: SF Pro Display;
    font-size: 15px;
    font-weight: 400;
    line-height: 18px;
    letter-spacing: 0em;
    text-align: right;
    color: #FFFFFF;
  }
}
</style>