<template>
    <table v-if="meetings.length > 0">
        <thead>
            Zajęcia (obecnie: {{meetings.length}})
            <tr>
                <th>Nazwa spotkania</th>
                <th>Opis spotkania</th>
                <th>Uczestnicy</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
            </tr>
        </tbody>
    </table>

    <table v-else>
        Nie ma spotkań
    </table>
</template>

<script>
export default {
    props: ["meetings", "username"],

    methods:{
        
        //todo
    }
}
</script>