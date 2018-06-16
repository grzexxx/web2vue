<template>
    <div v-if="adding">
        <new-meeting @add="addMeeting($event)"></new-meeting>
        <meeting-list :meetings="meetings"></meeting-list>
    </div>

    <div v-else>
        <button @click="enterAddingNewMeeting()">Nowe Spotkanie</button>
        <meeting-list :meetings="meetings" :username="username"
        @subscribe= "addNewParticipant($event)"
        @removeMeeting="removeMeeting($event)">
        </meeting-list>
    </div>

</template>

<script>
    import NewMeeting from "./NewMeeting.vue";
    import MeetingList from "./MeetingList.vue";

export default {
    props: ["username"],
    components: {NewMeeting, MeetingList},
    data(){
        return{
            meetings: [],
            adding: false
        };
    },

    methods: {
        addMeetning(meeting) {
            this.meetings.push(meeting);
            this.adding = false;
        },
        enterAddingNewMeeting(){
            this.adding = true;
        },
        addNewParticipant(meeting){

        },
        removeMeeting(meeting){

        },
        deleteParticipant(meeting){

        },

    }
    
}
</script>

