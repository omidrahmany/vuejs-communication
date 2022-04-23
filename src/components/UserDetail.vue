<template>
  <div>
    <div class="component">
      <h3>You may view the User Details here</h3>
      <p>Many Details</p>
      <p>Username: {{ reverseUserName() }}</p>
      <p>User age is: {{ userAge }}</p>
      <v-btn
          @click="resetFunction()"
          class="mx-2 mb-3"
          dark
          color="teal">Reset Username
      </v-btn>
    </div>
  </div>
</template>

<script>
import {eventBus} from "@/main";

export default {
  name: "UserDetail",
  props: {
    username: {
      type: String,
      required: true
    },
    resetFunction: Function,
  },
  data() {
    return {
      userAge: eventBus.userAge
    }
  },
  methods: {
    resetUsername() {
      this.$props.username = 'Omid';
      this.$emit('usernameWasReset', this.$props.username)
    },
    reverseUserName() {
      return this.$props.username.split("").reverse().join("");
    }
  },
  created() {
    eventBus.$on('ageWasEdited', (age) => {
      this.$data.userAge = age;
    });
  }
}
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
