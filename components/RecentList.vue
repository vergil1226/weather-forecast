<template>
  <section class="recent" elevation="0" v-if="recentList">
    <ul>
      <li v-for="(data, index) in recentList" :key="index">
        <v-card class="recent-card" @click="onCardClick(index)">
          <div class="address-info">
            <h1 class="recent-card__title">{{ data.name }}</h1>
            <p class="recent-card__time">
              {{ $moment.unix(data.dt).format("hh:mm A") }}
            </p>
            <p class="recent-card__description">
              {{ data.weather[0].description }}
            </p>
          </div>
          <div class="weather-info">
            <p class="recent-card__degree">
              {{ Math.round(data.main.temp - 273.15) }}&deg;
            </p>
            <p class="recent-card__range">
              High: {{ Math.round(data.main.temp_max - 273.15) }}&deg; Low:
              {{ Math.round(data.main.temp_min - 273.15) }}&deg;
            </p>
          </div>
          <!-- <v-container>
            <v-row no-gutters>
              <v-col cols="6">
              </v-col>
              <v-col cols="6">
              </v-col>
              <v-col cols="12">
              </v-col>
              <v-col cols="6">
              </v-col>
              <v-col cols="6">
              </v-col>
            </v-row>
          </v-container> -->
        </v-card>
      </li>
    </ul>
  </section>
</template>
<!-- need to add mounted, methods, and computed below-->
<script>
export default {
  computed: {
    recentList() {
      return this.$store.getters.getRecentList;
    },
  },
  methods: {
    onCardClick(index) {
      this.$store.dispatch("updateCardSelection", this.recentList.length - index - 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.recent {
  ul {
    list-style: none;
    padding-left: 0;
    display: flex;
    flex-direction: column;
    gap: 7px;
  }
  padding-left: 13px;
  padding-right: 16px;
}
.recent-card {
  border-radius: 20px;
  background: rgba(37, 102, 163, 0.2);
  box-shadow: none !important;
  border: 1px solid #377ce5;
  padding: 15px 24px 20px 15px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: space-between;
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
    text-transform: Capitalize;
    margin-bottom: 0;
  }
  &__degree {
    font-family: SF Pro Display;
    font-size: 50px;
    font-weight: 500;
    line-height: 60px;
    letter-spacing: 0em;
    text-align: center;
    color: #ffffff;
    margin-bottom: 0;
  }
  &__range {
    font-family: SF Pro Display;
    font-size: 15px;
    font-weight: 400;
    line-height: 18px;
    letter-spacing: 0em;
    text-align: right;
    color: #ffffff;
    margin-bottom: 0;
  }
  &::before {
    border-radius: 20px;
  }
  &:hover {
    background: rgba(37, 102, 163, 0.5);
  }
}
</style>
