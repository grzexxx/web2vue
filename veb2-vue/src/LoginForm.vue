<template>
   <div>
       <label>Podaj e-mail:</label>
       <input type="email" v-model="email">
     <!--  <label>Podaj hasło:</label>
       <input type="password" v-moder="password">
       <div v-if="email.match(/^[A-Za-z0-9\-_]+@[A-Za-z0-9\-_\.]+\.pl$/) ">Email prawidołwy</div>
       <div v-else="">Podaj prawidołwy e-mail na polskiej poczcie</div> -->
       <button @click="enter()">Zaloguj</button>

   </div>
</template>

<script>
export default {
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
  }
}
</script>