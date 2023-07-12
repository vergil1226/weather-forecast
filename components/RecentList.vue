<template>
  <div class="v-card">
    <ul class="no-bullets">
      <li>
        <v-card>
          <v-card class="weather-card" elevation="0">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <h1 class="weather-card__title">Tarpon Springs</h1>
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Sunny</p>
                  <p class="weather-card__degree">30</p>
                  <p class="weather-card__range">High: 34 Low: 28</p>
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
                  <p class="weather-card__time">9:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__degree">52</p>
                  <p class="weather-card__range">High: 52 Low: 34</p>
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
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Sunny</p>
                  <p class="weather-card__degree">32</p>
                  <p class="weather-card__range">High: 32 Low: 24</p>
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
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__degree">32</p>
                  <p class="weather-card__range">High: 36 Low: 21</p>
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
                  <p class="weather-card__time">9:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__degree">52</p>
                  <p class="weather-card__range">High: 52 Low: 34</p>
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
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__degree">32</p>
                  <p class="weather-card__range">High: 32 Low: 24</p>
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
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__degree">34</p>
                  <p class="weather-card__range">High: 36 Low: 21</p>
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
                  <p class="weather-card__time">11:22 AM</p>
                  <p class="weather-card__description">Mostly Cloudy</p>
                  <p class="weather-card__degree">32</p>
                  <p class="weather-card__range">High: 32 Low: 24</p>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-card>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      recentlocations: [
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
};
</script>

<style lang="scss" scoped>
.weather-card {
  width: 346px;
  height: 108px;
  background-color: #104084;
  &__title {
    font-family: SF Pro Display;
    font-size: 22px;
    font-weight: 500;
    line-height: 26px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__time {
    font-family: SF Pro Display;
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
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
.v-card .no-bullets{
  list-style: none;
}
</style>