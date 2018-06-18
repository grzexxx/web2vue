<template>
    <div v-if="isAdding">
       <new-meeting-form @added="addNewMeeting($event)"></new-meeting-form>
        <meetings-list :meetings="meetings"></meetings-list>
    </div>

    <div v-else>
      <button @click="addingNewMeeting()">Nowe Spotkanie</button>
       <meetings-list>  :meetings="meetings" :username="username"
       
       </meetings-list>
    </div>
</template>

<script>
import NewMeetingForm from "./NewMeetingForm";
import MeetingsList from "./MeetingsList";
export default {
  props: ["username"],
  components: { NewMeetingForm, MeetingsList },
  data() {
    return {
      meetings: [],
      isAdding: false
    };
  },
  methods: {
    addNewMeeting(meeting) {
      this.meetings.push(meeting);
      this.isAdding=false;
    },
    addingNewMeeting() {
      this.isAdding = true;
   //todo
    },
  }
};
</script>

