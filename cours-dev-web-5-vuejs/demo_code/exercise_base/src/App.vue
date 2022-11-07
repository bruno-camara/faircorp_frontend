<template>
  <div id="app">
    <header>
      <div class="title">Smart Building Managment</div>
    </header>

    <section class="main-content w-50 mx-auto">
    
    <main-navigation></main-navigation>
    <windows-list></windows-list>
    <window-form></window-form>

      
    </section>

  </div>
</template>

<script>
import MainNavigation from './components/MainNavigation.vue';
import WindowsList from './components/WindowsList.vue';
import WindowForm from './components/WindowForm.vue';
export default {
  name: 'App',
  components: {
  MainNavigation,
  WindowsList,
  WindowForm
  }
}
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.icon {
  position: relative;

  &.open {
    font-size: 12px;
    top: -3px;
    color: #198754;
  }

  &.closed {
    color: #dc3545;
  }
}

.window {
  .top-row {
    cursor: pointer;
  }
}
</style>
