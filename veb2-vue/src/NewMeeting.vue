<template>

    <from @submit.prevent="addMeeting()">
        <h2>Dodaj nowe spotkanie:</h2>
        <label>Nazwa spotkania:</label>
        <input type="text" v-model="newMeeting.name">
        
        <label>Opis spotkania:</label>
        <textarea v-model="newMeeting.description"></textarea>
           <div>
            <button>Dodaj spotkanie</button>
            <em v-if="shortName" style = "color:red"> 
                Za krótka nazwa </em>
        </div>
    </from>
</template>

<script>
export default {
    data() {
        return{
            newMeeting: {
                participants:[],
            },
            shortName: false
        }
    },
             methods: {
    addMeeting() {
      if (!this.newMeeting.name || this.newMeeting.name.length < 1) {
        this.hasEmptyName = true;
      } else {
        this.$emit("added", this.newMeeting);
            }
        }
    }
}
</script>