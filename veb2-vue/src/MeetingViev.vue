<template>
    <div v-if="adding">
        <new-meetning @add="addMeeting($event)"></new-meetning>
        <meeting-list :meetings="meetings"></meeting-list>
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
        }
    },

    methods: {
        addMeetning(meetning) {
            this.addMeetning.push(meetning);
            this.adding;
        }
    }
    
}
</script>

