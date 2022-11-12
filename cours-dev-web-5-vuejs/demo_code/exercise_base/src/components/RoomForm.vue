<template>
  <!-- based off https://serversideup.net/post-put-patch-requests-with-vuejs-and-axios/ -->
  <div class="room border border-secondary rounded p-2 mb-2">
      <label for="name">Name:</label><br>
      <input type="text" v-model = "form.name"><br>
      <label for="bname">Building Name:</label><br>
      <input type="text" v-model = "form.buildingName"><br>
      <label for="bid">Building Id:</label><br>
      <input type="number" v-model = "form.buildingId"><br><br>
      <button v-on:click="createRoom()">Submit</button>
  </div>
</template>

<script>
import axios from 'axios';
import {API_HOST} from '../config';

export default {
  name: 'RoomForm',
  data(){
        return {
            form: {
                name: '',
                buildingName: '',
                buildingId: 0
            }
        }
    },
  methods: {
    async createWindow() {
      let response = await axios.post(`${API_HOST}/api/rooms`, this.form);
      let newRoom = response.data;
      this.$emit('room-created', newRoom);
    }
  }
}
</script>
