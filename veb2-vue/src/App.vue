<template>
  <div id="app">
<h1> Witaj w systemie zapisów na zajęcia</h1>
Zaloguj się e-mailem <input type="email" v-model="email">
  <button @click="login()">Zaloguj</button>


   <!-- <h1>Twój e-mail to:{{ email.length }} {{email }} </h1>
   <input type="email" v-model="email">
   <div v-if="email.match(/^[A-Za-z0-9\-_]+@[A-Za-z0-9\-_\.]+\.pl$/) ">Pasuje</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button> -->
   
<!-- [^A-Za-z0-9\-_]+@[A-Za-z0-9\-_\.]+\.pl$/ -->

  </div>

 <!-- gdfgs -->
  <!-- <div v-if="email.match(/^[A-Za-z0-9\-_]+@[A-Za-z0-9\-_\.]+\.pl$/) ">Pasuje</div> -->
  
</template>


<script>
export default {  //specyfikacja komponentyu
  name: 'app',
  data () {
    return {
      email: ''
    }
   },
   methods: {
  login() {
    alert("zalogowałeś sie jako" +this.email )
  }
}
}
</script>

<style lang="scss">


</style>
