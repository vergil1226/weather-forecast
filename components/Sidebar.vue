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
          <RecentList />
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
    <Mainview />
  </v-app>
</template>




<script>
import RecentList from './RecentList.vue';
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

</style>