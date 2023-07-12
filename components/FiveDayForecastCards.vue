<template>
  <div>
    <v-card class="forecast-card" elevation="0" color="#5096FF">
      <h3 class="forecast-card__title">5-Day Forecast</h3>
      <div class="d-flex">
        <ol class="forecast-card-list">
          <li class="forecast-card-list__items">
            <v-card class="forecast-card">
              <v-container>
                <v-row>
                  <v-col cols="12">
                    <h2 class="forecast-card__title">5-Day Forecast</h2>
                    <p class="forecast-card-day">Monday</p>
                    <v-icon>mdi-google-circles-extended</v-icon>
                    <p class="forecast-card__range">13</p>
                    <p class="forecast-card__range">10</p>
                  </v-col>
                  <v-col cols="12">
                    <h2 class="forecast-card__title">5-Day Forecast</h2>
                    <p class="forecast-card-day">Tuesday</p>
                    <v-icon>mdi-google-circles-extended</v-icon>
                    <p class="forecast-card__range">17</p>
                    <p class="forecast-card__range">12</p>
                  </v-col>
                  <v-col cols="12">
                    <h2 class="forecast-card__title">5-Day Forecast</h2>
                    <p class="forecast-card-day">Wednesday</p>
                    <v-icon>mdi-google-circles-extended</v-icon>
                    <p class="forecast-card__range">21</p>
                    <p class="forecast-card__range">18</p>
                  </v-col>
                </v-row>
              </v-container>
            </v-card>
          </li>
        </ol>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.forecast-card {
  background-color: #104084;
  &__title {
    font-family: SF Pro Display;
    font-size: 20px;
    font-weight: 700;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__day {
    font-family: Alegreya Sans;
    font-size: 18px;
    font-weight: 700;
    line-height: 22px;
    letter-spacing: 0em;
    text-align: left;
    color: #ffffff;
  }
  &__range{
    font-family: Alegreya Sans;
    font-size: 18px;
    font-weight: 500;
    line-height: 22px;
    letter-spacing: 0em;
    text-align: center;
    color: #FFFFFF;
  }
}
</style>