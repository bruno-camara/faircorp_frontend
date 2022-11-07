<template>
  <div class="windows-list pt-3">
    <windows-list-item
    v-for="window in windows"
          :window="window"
          :key="window.id"
          @window-updated="updateWindow" ></windows-list-item>
  </div>
</template>

<script>
import axios from 'axios';
import {API_HOST} from '../config';
import WindowsListItem from './WindowsListItem.vue';
export default {
  name: 'WindowsList',
  components: {
  WindowsListItem
  },
  data: function() {
     return {
       windows: []
     }
  },
  created: async function() {
    let response = await axios.get(`${API_HOST}/api/windows`);
    let windows = response.data;
    this.windows = windows;
  },
  methods: {
    updateWindow(newWindow) {
      /* Find the place of window object with the same Id in the array, and replace it */
      let index = this.windows.findIndex(window => window.id === newWindow.id);
      this.windows.splice(index, 1, newWindow);
    },
    async refresh() {
      /* We delete a window so get the windows again */
      console.log("Refreshing");
      let response = await axios.get(`${API_HOST}/api/windows`);
      let windows = response.data;
      this.windows = windows;
    }
  }
}
</script>
