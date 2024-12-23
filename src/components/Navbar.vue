<template>
    <nav>
      <ul>
        <li><a href="#">Bangun Datar</a></li>
        <li><a href="#">Kuis</a></li>
        <li><a href="#">Manajemen Kuis</a></li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'NavBar'
  };
  </script>
  
  <style scoped>
  nav {
    background-color: #ffcc00;
    padding: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    font-family: 'Comic Sans MS', cursive, sans-serif;
  }
  
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: space-around;
  }
  
  li a {
    color: #333;
    text-decoration: none;
    padding: 10px 20px;
    transition: background-color 0.3s;
    font-size: 18px;
  }
  
  li a:hover {
    background-color: #ffdd00;
  }
  </style>
  