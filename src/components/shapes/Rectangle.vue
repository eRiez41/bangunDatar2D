<template>
    <div class="shape-container">
      <div class="shape">
        <div class="side top">Sisi Atas</div>
        <div class="side right">Sisi Kanan</div>
        <div class="side bottom">Sisi Bawah</div>
        <div class="side left">Sisi Kiri</div>
      </div>
      <p>Persegi panjang adalah bangun datar dengan empat sisi dan empat sudut yang sama besar.</p>
      <p>Rumus Luas: {{ panjang && lebar ? `${panjang} * ${lebar} = ${luas}` : 'panjang * lebar' }}</p>
      <p>Rumus Keliling: {{ panjang && lebar ? `2 * (${panjang} + ${lebar}) = ${keliling}` : '2 * (panjang + lebar)' }}</p>
      <input v-model="panjang" type="number" placeholder="Masukkan panjang" @input="calculate">
      <input v-model="lebar" type="number" placeholder="Masukkan lebar" @input="calculate">
    </div>
  </template>
  
  <script>
  export default {
    name: 'RectangleShape',
    data() {
      return {
        panjang: null,
        lebar: null
      };
    },
    computed: {
      luas() {
        return this.panjang && this.lebar ? this.panjang * this.lebar : 0;
      },
      keliling() {
        return this.panjang && this.lebar ? 2 * (this.panjang + this.lebar) : 0;
      }
    },
    methods: {
      calculate() {
        if (this.panjang < 0 || this.lebar < 0) {
          this.panjang = null;
          this.lebar = null;
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
    width: 300px;
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
  