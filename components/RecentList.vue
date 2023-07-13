<template>
  <section class="recent" elevation="0">
    <ul class="no-bullets">
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Tarpon Springs</h1>
                  <p class="weather-card__degree">30&deg;</p>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Sunny</p>
                  <p class="weather-card__range">High: 34&deg; Low: 28&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
          <!-- add a v-for loop that through all the recent locations in vuex once that is done do not need the 7 other cards of code-->
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Denver</h1>
                  <p class="weather-card__degree">52&deg;</p>
                  <p class="weather-card__time">9:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__range">High: 52&deg; Low: 34&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Tampa</h1>
                  <p class="weather-card__degree">32&deg;</p>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Sunny</p>
                  <p class="weather-card__range">High: 32&deg; Low: 24&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Jacksonville</h1>
                  <p class="weather-card__degree">32&deg;</p>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__range">High: 36&deg; Low: 21&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Denver</h1>
                  <p class="weather-card__degree">52&deg;</p>
                  <p class="weather-card__time">9:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__range">High: 52&deg; Low: 34&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Tampa</h1>
                  <p class="weather-card__degree">32&deg;</p>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__range">High: 32&deg; Low: 24&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Jacksonville</h1>
                  <p class="weather-card__degree">34&deg;</p>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__range">High: 36&deg; Low: 21&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Tampa</h1>
                  <p class="weather-card__degree">32&deg;</p>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__range">High: 32&deg; Low: 24&deg;</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
    </ul>
  </section>
</template>
<!-- need to add mounted, methods, and computed below-->
<script>
export default {
  data() {
    return {
      locationData: {
        locationID: null,
        id: null,
      },
      selected_location: [],
      locations: [
        {
          City: "Tarpon Springs",
          State: "Florida",
        },
        {
          City: "Denver",
          State: "Colorado",
        },
        {
          City: "Tampa",
          State: "Florida",
        },
        {
          City: "Jacksonville",
          State: "Florida",
        },
        {
          City: "Denver",
          State: "Colorado",
        },
        {
          City: "Tampa",
          State: "Florida",
        },
        {
          City: "Jacksonville",
          State: "Florida",
        },
        {
          City: "Tampa",
          State: "Florida",
        },
      ],
    };
  },
  methods() {

  },
  computed() {

  },
};
</script>

<style lang="scss" scoped>
.weather-card {
  max-width: 346px;
  background-color: #104084;
  &__title {
    font-family: SF Pro Display;
    font-size: 22px;
    font-weight: 500;
    line-height: 26px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
    margin-bottom: 3px;
  }
  &__time {
    font-family: SF Pro Display;
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
    margin-bottom: 8px;
  }
  &__description {
    font-family: SF Pro Display;
    font-size: 16px;
    font-weight: 500;
    line-height: 19px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__degree {
    font-family: SF Pro Display;
    font-size: 50px;
    font-weight: 500;
    line-height: 60px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
  }
  &__range {
    font-family: SF Pro Display;
    font-size: 15px;
    font-weight: 400;
    line-height: 18px;
    letter-spacing: 0em;
    text-align: right;
    color: #ffffff;
  }
}
.recent .no-bullets {
  list-style: none;
}
</style>