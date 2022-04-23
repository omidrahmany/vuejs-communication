<template>
  <div>
    <div class="component">
      <h3>You may edit the User here</h3>
      <p>Edit me!</p>
      <p>current age: {{ age }}</p>
      <v-btn
          class="mx-2"
          dark
          small
          color="pink"
          @click="editAge"
      >
        Edit User Age
      </v-btn>
    </div>
  </div>
</template>

<script>
import {eventBus} from "@/main";

export default {
  name: "UserEdit",
  data(){
    return {
      age: eventBus.userAge
    }
  },
  methods: {
    editAge() {
      this.age = 30;
      // eventBus.$emit('ageWasEdited', this.age);
      eventBus.changeAge(this.age);
    }
  }
}
</script>

<style scoped>
div {
  background-color: lightgreen;
}
</style>
