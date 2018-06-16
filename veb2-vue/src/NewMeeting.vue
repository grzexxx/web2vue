<template>
    <from @submit.prevent="addMeeting()">
        <h2>Dodaj nowe spotkanie:</h2>
        <label>Nazwa spotkania:</label>
        <input type="text" v-model="newMeeting.name" v-bind.class="{'is-valid': NoName }">
        
        <label>Opis spotkania:</label>
        <textarea v-model="newMeeting.descript"></textarea>
            <div>
            <button>Dodaj spotkanie</button>
            </div>
    </from>
</template>


<script>
export default {

    methods:{

        addMeetnig() {
            if(!this.newMeeting.name|| this.newMeeting.name.length <3){
             this.shortName = true;
            }
            else {
             this.$emit("add", this.addMeetnig)
            }
        }
    }
}
</script>