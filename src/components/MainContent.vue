<template>
    <main>
      <SquareShape v-if="selectedShape === 'square'" />
      <RectangleShape v-if="selectedShape === 'rectangle'" />
      <CircleShape v-if="selectedShape === 'circle'" />
    </main>
  </template>
  
  <script>
  import SquareShape from './shapes/Square.vue';
  import RectangleShape from './shapes/Rectangle.vue';
  import CircleShape from './shapes/Circle.vue';
  
  export default {
    components: {
      SquareShape,
      RectangleShape,
      CircleShape
    },
    props: {
      selectedShape: String
    }
  };
  </script>
  
  <style scoped>
  main {
    padding: 20px;
    flex-grow: 1;
    background-color: #fff;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    font-family: 'Comic Sans MS', cursive, sans-serif;
  }
  </style>
  