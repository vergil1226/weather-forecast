<template>
  <!--- set to refresh every 5 minutes use built in js interval in the mounted lifecycle hook - need to update the timeout method-->
  <v-app>
    <v-main>
      <v-card>
        <v-navigation-drawer
          class="app__sidebar"
          color="#104084"
          width="375px"
          dark
          permanent
        >
          <v-list>
            <v-card class="app__card">
              <v-text-field
                v-model="searchQuery"
                loading="isloading"
                prepend-inner-icon="mdi-map-marker-outline"
                placeholder="Add Location..."
                @keyup.enter="searchLocation"
                class="app__search"
              >
              </v-text-field>
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
</template>


<script>
import RecentList from './RecentList.vue';
export default {
  components: { RecentList },
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
//     {
//       setTimeout(() => {
//         location.reload();
//       }, 5 * 60 * 1000)
//     }
// }
}
}
</script>

<style lang="scss" scoped>
.app__search{
  max-width: 346px;
}
</style>