<template>
<table v-if="meetings.length > 0">
        <thead>
            Spotkania (ilość:{{meetings.length}})
            <tr>
                <th>Nazwa spotkania</th>
                <th>Opis</th>
                <th>Uczestnicy </th>
                <th></th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name" align="left">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
                <td>
                    <li v-for="participant in meeting.participants" :key="participant" >
                        {{participant}}
                    </li>
                </td>
                   
            </tr>
        </tbody>
    </table>
    <table v-else>
        Brak spotkań!
    </table>
</template>

<script>
export default {
    props: ["meetings", "username"],

    methods:{
      //todo
  }
};
</script>