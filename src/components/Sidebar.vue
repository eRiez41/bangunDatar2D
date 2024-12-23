<template>
    <aside>
      <ul>
        <li><a href="#" @click.prevent="selectShape('square')">Persegi</a></li>
        <li><a href="#" @click.prevent="selectShape('rectangle')">Persegi Panjang</a></li>
        <li><a href="#" @click.prevent="selectShape('circle')">Lingkaran</a></li>
        <li><a href="#">Segitiga</a></li>
      </ul>
    </aside>
  </template>
  
  <script>
  export default {
    name: 'SideBar',
    methods: {
      selectShape(shape) {
        this.$emit('shape-selected', shape);
      }
    }
  };
  </script>
  
  <style scoped>
  aside {
    background-color: #ffcc00;
    padding: 20px;
    width: 200px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    font-family: 'Comic Sans MS', cursive, sans-serif;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li a {
    text-decoration: none;
    color: #333;
    display: block;
    padding: 10px;
    transition: background-color 0.3s;
    font-size: 18px;
  }
  
  li a:hover {
    background-color: #ffdd00;
  }
  </style>
  