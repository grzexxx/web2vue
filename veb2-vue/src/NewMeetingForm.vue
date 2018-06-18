<template>
    <form @submit.prevent="addNewMeeting()">
            <h2>Dodaj nowe spotkanie:</h2>
            <label>Nazwa</label>
            <input type="text" v-model="newMeeting.name" v-bind:class="{ 
              'is-valid': shortName }">
            <label>Opis</label>
            <textarea v-model="newMeeting.description"></textarea>       
            <div class="clearfix">
                
                  <button>Dodaj</button>
                
                <em class="float-left" v-if="shortName" style="color:pink"> Za krótka nazwa</em>
            </div>
        </form>
</template>

<script>
export default {
  data() {
    return {
      newMeeting: {
        participants:[],
      },
      shortName: false
    };
  },
  methods: {
    addNewMeeting() {
      if (!this.newMeeting.name || this.newMeeting.name.length < 3) {
        this.shortName = true;
      } else {
        this.$emit("added", this.newMeeting);
      }
    }
  }
};
</script>
