<template>
    <div class="shape-container">
      <div class="shape">
        <div class="side top">Sisi Atas</div>
        <div class="side right">Sisi Kanan</div>
        <div class="side bottom">Sisi Bawah</div>
        <div class="side left">Sisi Kiri</div>
      </div>
      <p>Persegi adalah bangun datar dengan empat sisi yang sama panjang dan empat sudut yang sama besar.</p>
      <p>Rumus Luas: {{ sisi ? `${sisi} * ${sisi} = ${luas}` : 'sisi * sisi' }}</p>
      <p>Rumus Keliling: {{ sisi ? `4 * ${sisi} = ${keliling}` : '4 * sisi' }}</p>
      <input v-model="sisi" type="number" placeholder="Masukkan panjang sisi" @input="calculate">
    </div>
  </template>
  
  <script>
  export default {
    name: 'SquareShape',
    data() {
      return {
        sisi: null
      };
    },
    computed: {
      luas() {
        return this.sisi ? this.sisi * this.sisi : 0;
      },
      keliling() {
        return this.sisi ? 4 * this.sisi : 0;
      }
    },
    methods: {
      calculate() {
        if (this.sisi < 0) {
          this.sisi = null;
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
  
  .top {
    top: -30px;
    left: 50%;
    transform: translateX(-50%);
  }
  
  .right {
    top: 50%;
    right: -80px;
    transform: translateY(-50%) rotate(90deg);
  }
  
  .bottom {
    bottom: -30px;
    left: 50%;
    transform: translateX(-50%);
  }
  
  .left {
    top: 50%;
    left: -80px;
    transform: translateY(-50%) rotate(90deg);
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
  