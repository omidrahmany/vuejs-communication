<template>
  <v-container :style="{background: 'lightblue'}">
    <v-row class="component">
      <v-col cols="12">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <v-btn
            @click="changeName"
            class="mx-2 mb-3"
            dark
            color="teal">Change my Name
        </v-btn>
        <p>My name is {{ userName }}</p>
        <hr>
        <v-row>
          <v-col
              cols="12"
              xs="12"
              sm="6">
<!--            <UserDetail :username="userName"
                        :reset-function="resetUsername"
                        :user-age="userAge"/>-->
            <UserDetail :username="userName"
                        :reset-function="resetUsername"
                        />
          </v-col>
          <v-col
              xs="12"
              sm="6">
            <!--            <UserEdit @ageWasEdited="userAge = $event"
                                  :current-age="userAge"/>-->
            <UserEdit />
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import UserDetail from "@/components/UserDetail";
import UserEdit from "@/components/UserEdit";

export default {
  name: "AppUser",
  components: {UserEdit, UserDetail},
  data() {
    return {
      userName: 'Omid'
    }
  },
  methods: {
    resetUsername() {
      this.$data.userName = 'Omid';
    },
    changeName() {
      return this.$data.userName = 'Kosar'
    },

  }
}
</script>

<style scoped>

</style>
