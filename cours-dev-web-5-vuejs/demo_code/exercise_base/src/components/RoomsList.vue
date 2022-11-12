<template>
      <div class="rooms-list pt-3">
    <rooms-list-item
    v-for="room in rooms"
          :room="room"
          :key="room.id"
          @room-updated="updateRoom"
          @room-deleted="refresh"></rooms-list-item>
    <room-form @room-created="createRoom"></room-form>
  </div>
</template>

<script>

import axios from 'axios';
import {API_HOST} from '../config';
import RoomsListItem from './RoomsListItem.vue';
import RoomForm from './RoomForm.vue';

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
