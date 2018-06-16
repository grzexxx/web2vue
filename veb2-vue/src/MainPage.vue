<template>
  <div>
    <div>
        <h2>Zalogowałeś się jako: {{username}}!</h2>         
        <button @click="logout()">Wyloguj</button>          
    </div>
  </div>
</template>


<script>
export default {

   components: {
   },
   
     methods: {
        logout() {
            this.$emit("logout");
            }
        }
    }

</script>