<template>
  <div id="app">
    <h1> Witaj w systemie zapisów na zajęcia</h1>
    <div v-show="!isAuthebticated">
      <login-form @login="login($event)"></login-form>
    </div>

      <div v-show="isAuthebticated">
      <main-page @logout="logout" :username="authenticatedUsername"> </main-page>
    </div>
  </div>
</template>


<script>
import "milligram";

import LoginForm from "./LoginForm";
import MainPage from "./MainPage";


export default {
  //specyfikacja komponentyu
  name: "app",
  components: { LoginForm, MainPage},
  data() {

    return {
      email: "",
      isAuthebticated: false,
      authenticatedUsername:""
    };
  },
  methods: {
    login(username) {
      this.isAuthebticated = true;
      this.authenticatedUsername = username;
    },
    logout() {
      this.isAuthebticated = false;
      this.authenticatedUsername = "";
    }
  }
};
</script>

<style lang="scss">
h1 {
  color: deeppink;
}
</style>
