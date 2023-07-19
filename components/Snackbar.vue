<template>
  <!-- need to hide the snackbar-->
  <section class="Snackbar" elevation="0">
    <v-btn dark @click="snackbar = true" elevation="0"> Open Snackbar </v-btn>
    <v-snackbar v-model="snackbar">
      {{ text }}

      <template v-slot:action="{ attrs }">
        <v-btn
          color="pink"
          text
          v-bind="attrs"
          @click="snackbar = false"
          elevation="0"
        >
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </section>
</template>

<script>
export default {
  data() {
    return {
      text: ", Vue!",
      snackbar: true,
    };
  },
};
</script>

<style lang="scss" scoped>
.Snackbar {
  max-width: 346px;
  padding: 14px 57px 0 0;
  display: none;
}
</style>
