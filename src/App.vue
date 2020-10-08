<template>
  <v-app>
    <TopNav />
    <v-main>
      <router-view></router-view>
    </v-main>
    <v-snackbar
      v-model="$store.state.snackbar.show"
      :multi-line="true"
      :right="true"
      :top="true"
      :timeout="6000"
      :color="$store.state.snackbar.variant"
    >
      {{ $store.state.snackbar.message }}
      <v-btn dark text @click="$store.commit('updateSnackbar', false)"
        >Close</v-btn
      >
    </v-snackbar>
  </v-app>
</template>

<script>
import TopNav from "./components/TopNav";

export default {
  name: "App",

  components: {
    TopNav,
  },
};
</script>
