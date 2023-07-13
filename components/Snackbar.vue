<template>
  <!-- need to hide the snackbar-->
  <section class="Snackbar" elevation="0">
    <v-btn
      dark
      @click="snackbar = true"
      elevation="0"
    >
      Open Snackbar
    </v-btn>
    <v-snackbar
      v-model="snackbar"
    >
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
  export default {}
  //   data() {
  //     return {
  //       snackbar: []
  //     }
  //   };

  //   function showSnackbar(message) {
  //     var snackbar = document.getElementById("snackbar");
  //     snackbar.innerText = message;
  //     snackbar.style.display = "block"
    
  //   setTimeout(function () {
  //     snackbar.style.display = "none";
  //   }, 5*60* 1000)
  //   }
  //   showSnackbar("Error: Something went wrong!");
  // }
</script>

<style lang="scss" scoped>
.Snackbar {
  max-width: 346px;
  padding: 14px 57px 0 0;
}

</style>
