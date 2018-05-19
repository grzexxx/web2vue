<template>
  <div id="app">
    <h1> Witaj w systemie zapisów na zajęcia</h1>
<div v-if="isAuthebticated">

<h2>Zalogowałeś się jako: {{email}}</h2>
 <button @click="LogOut()">Wyloguj</button>


</div>

<div v-else>

Zaloguj się e-mailem <input type="email" v-model="email">
  <button @click="logIn()">Zaloguj</button>


</div>





   <!-- <h1>Twój e-mail to:{{ email.length }} {{email }} </h1>
   <input type="email" v-model="email">
   <div v-if="email.match(/^[A-Za-z0-9\-_]+@[A-Za-z0-9\-_\.]+\.pl$/) ">Pasuje</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button> -->
   
<!-- [^A-Za-z0-9\-_]+@[A-Za-z0-9\-_\.]+\.pl$/ -->

  </div>




</template>


<script>
import LoginForm from "./LoginForm";
import "milligram";


export default {  //specyfikacja komponentyu

  name: 'app',
  components: {LoginForm},
  data () {
    return {
      email: '',
      isAuthebticated: false
    }
   },
   methods: {
  logIn() {
   this.isAuthebticated = true
  },
  LogOut() {
    this.isAuthebticated = false
  }
},

}



</script>

<style lang="scss">
h1{
  color: deeppink
}

</style>
