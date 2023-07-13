<template>
  <!--- set to refresh every 5 minutes use built in js interval in the mounted lifecycle hook - need to update the timeout method-->
  <section class="sidebar" elevation="0" style="height: 100%;">
  <v-app>
    <v-main>
      <v-card elevation="0">
        <v-navigation-drawer
          class="app__sidebar"
          color="#104084"
          width="375px"
          dark
          permanent
        >
          <v-list>
            <v-card class="app__card" elevation="0" @click="emit('someEvent')">
              <v-text-field
                v-model="searchQuery"
                loading="isloading"
                prepend-inner-icon="mdi-map-marker-outline"
                placeholder="Add Location..."
                @keyup.enter="searchLocation"
                class="app__search"
                solo
                rounded
              >
              </v-text-field>
              <Snackbar />
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
      <recent-list />
    </v-main>
  </v-app>
  </section>
</template>


<script>
import RecentList from './RecentList.vue';
import SnackbarVue from './Snackbar.vue';

export default {
  components: { RecentList },
  data() {
    return {
      searchQuery: '',
    };
  },
  mounted() {
    this.getGeolocation();
  },
  methods: {
    async getGeolocation() {
      try {
        const { data } = await this.$axios.$get("/geolocation");

        const response = this.$normalize(data);

        this.geolocation = response.map((item) => ({
          ...item,
          clicked: item.located,
        }));
      } catch (error) {
        console.log(error);
      }
    },
    moveCard(item) {
      item.clicked = !item.clicked;
      setTimeout(() => {
      item.located = !item.located;
      this.mapToDatabase(item);
      }, 5*60* 1000);
    }
    // searchLocation() {
    //   // Here you can perform the search logic for the entered location
    //   // You can access the entered location via `this.searchQuery`
    //   console.log("Search query:", this.searchQuery);
    // },
},
computed: {
  ...mapFields(["loading"])
}
}
</script>

<style lang="scss" scoped>
.app__search{
  max-width: 346px;
}
</style>