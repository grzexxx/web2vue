<template>
  <div>
    <div>
        <h2>Zalogowałeś się jako: {{username}}</h2>         
        <button @click="logout()">Wyloguj</button>          
    </div>
    
    <meeting-viev :username="username"></meeting-viev>
  </div>
</template>

<script>
import MeetingViev from "./MeetingViev";

export default {

   components: {
       MeetingViev
   },
   props: ["username"],
   data() {
       return{};
   },

     methods: {
        logout() {
            this.$emit("logout");
            }
        }
    }

</script>