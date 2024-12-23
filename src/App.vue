<template>
  <div id="app">
    <Navbar />
    <div class="content">
      <Sidebar @shape-selected="selectShape" />
      <MainContent :selectedShape="selectedShape" />
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Sidebar from './components/Sidebar.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Sidebar,
    MainContent
  },
  data() {
    return {
      selectedShape: 'square' // Default to square
    };
  },
  methods: {
    selectShape(shape) {
      this.selectedShape = shape;
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
}

.content {
  display: flex;
}
</style>
