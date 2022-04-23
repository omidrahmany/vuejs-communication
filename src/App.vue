<template>
  <v-app>
    <v-main>
      <app-user />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import User from "@/components/User.vue";

export default Vue.extend({
  name: 'App',
  components: {
   appUser: User,
  },

  data: () => ({
    //
  }),
});
</script>

<style>
div.component {
  border: 1px solid black;
  padding: 30px;
}
</style>
