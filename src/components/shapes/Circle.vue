<template>
    <div class="shape-container">
      <div class="shape">
        <div class="side radius">Jari-jari</div>
        <div class="side diameter">Diameter</div>
      </div>
      <p>Lingkaran adalah bangun datar dengan semua titik yang berjarak sama dari pusat.</p>
      <p>Rumus Diameter: 2 * jari-jari = {{ diameter }}</p>
      <p>Rumus Luas (jari-jari): π * jari-jari^2 = {{ luasJariJari }}</p>
      <p>Rumus Luas (diameter): π * (diameter/2)^2 = {{ luasDiameter }}</p>
      <p>Rumus Keliling (jari-jari): 2 * π * jari-jari = {{ kelilingJariJari }}</p>
      <p>Rumus Keliling (diameter): π * diameter = {{ kelilingDiameter }}</p>
      <input v-model="jariJari" type="number" placeholder="Masukkan jari-jari" @input="calculate">
    </div>
  </template>
  
  <script>
  export default {
    name: 'CircleShape',
    data() {
      return {
        jariJari: null
      };
    },
    computed: {
      diameter() {
        return this.jariJari ? 2 * this.jariJari : 0;
      },
      luasJariJari() {
        return this.jariJari ? Math.PI * Math.pow(this.jariJari, 2) : 0;
      },
      luasDiameter() {
        return this.jariJari ? Math.PI * Math.pow(this.diameter / 2, 2) : 0;
      },
      kelilingJariJari() {
        return this.jariJari ? 2 * Math.PI * this.jariJari : 0;
      },
      kelilingDiameter() {
        return this.jariJari ? Math.PI * this.diameter : 0;
      }
    },
    methods: {
      calculate() {
        if (this.jariJari < 0) {
          this.jariJari = null;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .shape-container {
    text-align: center;
    margin: 20px;
    font-family: 'Comic Sans MS', cursive, sans-serif;
  }
  
  .shape {
    position: relative;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    border: 4px solid #ff6600;
    margin: 20px auto;
    background-color: #ffcc00;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }
  
  .side {
    position: absolute;
    background-color: rgba(0, 0, 0, 0.1);
    color: #ff6600;
    font-size: 14px;
    padding: 4px;
    font-weight: bold;
  }
  
  .radius {
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    border-left: 2px dashed #ff6600;
    height: 100px;
    width: 0;
  }
  
  .diameter {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-top: 2px solid #ff6600;
    width: 200px;
    height: 0;
  }
  
  input {
    margin-top: 10px;
    padding: 10px;
    border: 2px solid #ff6600;
    border-radius: 8px;
    transition: border-color 0.3s;
    font-size: 16px;
  }
  
  input:focus {
    border-color: #ff9900;
  }
  </style>
  