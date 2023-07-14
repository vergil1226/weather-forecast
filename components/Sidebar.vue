<template>
  <!--- set to refresh every 5 minutes use built in js interval in the mounted lifecycle hook - need to update the timeout method-->
  <section class="sidebar" float elevation="0">
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
        <!-- need to add fab -->
          <v-list>
            <v-card class="sidebar__card" color="#104084" elevation="0" @click="emit('someEvent')">
              <v-text-field
                v-model="searchQuery"
                loading="isloading"
                prepend-inner-icon="mdi-map-marker-outline"
                placeholder="Add Location..."
                @keyup.enter="searchLocation"
                class="app__search"
                solo
                rounded
                max-width="346px"
                color="#104084"
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
import Snackbar from './Snackbar.vue';

export default {
  components: { RecentList, Snackbar},
  data() {
    return {
      searchQuery: '',
    };
  },
  props: {
    width: {
      type: [Number, String],
    }
  },
}
    // searchLocation() {
    //   // Here you can perform the search logic for the entered location
    //   // You can access the entered location via `this.searchQuery`
    //   console.log("Search query:", this.searchQuery);
    // },



</script>

<style lang="scss" scoped>
.sidebar {
  max-width: 375px;
  &__card{
    padding-top: 30px;
    padding-bottom: 27px;
    box-sizing: border-box;
  }
}
</style>