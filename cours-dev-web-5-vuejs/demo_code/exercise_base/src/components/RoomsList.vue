<template>
    
</template>

<script>

import axios from 'axios';
import {API_HOST} from '../config';
import WindowsListItem from './RoomsListItem.vue';
import WindowForm from './RoomForm.vue';

export default{
    name: 'RoomsList',
    components: {
        RoomsListItem,
        RoomForm,
    },
    data: function() {
        return{
            rooms: []
        }
    },
    created: async function() { 
        let response = await axios.get(`${API_HOST}/api/rooms`);
        let rooms = response.data;
        this.rooms = rooms;
    },
    methods: {
        createRoom(newRoom){
            this.rooms.push(newRoom);
        },
        async refresh(){
            console.log("Refreshing");
            let response = await axios.get(`${API_HOST}/api/rooms`);
            let rooms = response.data;
            this.rooms = rooms;
        }
    }
}

</script>
