<template>

</template>

<script>

import axios from 'axios';
import {API_HOST} from '../confg';
 export default{
     name: 'RoomsListItem',
     props: ['room'],
     data: function (){
         return {isExpanded: false}
     },
     methods: {
         toggleExpand() {
             this.isExpanded = !this.isExpanded;
         },
         async switchRoom() {
             let response = await axios.put(`${API_HOST}/api/rooms/${this.room.id}/switch`);
             let updateRoom = response.data;
             this.$emit('room-update', updateRoom);
         },

         async deleteWindow(){
             let response = await axios.delete(`${API_HOST}/api/rooms/${this.window.id}`);
             this.$emit('room-deleted');
         }

     }
 }

</script> 