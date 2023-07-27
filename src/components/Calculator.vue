
<script>
export default {
  data() {
    return {
      inputValues: [0, 0, 0, 0, 0, 0], // Array to store the values of all input boxes
    };
  },
  methods: {
      end_turn() {
      // Log all input values to the console
      this.inputValues=[0, 0, 0, 0, 0, 0];
    },
    addValue(index, amount) {
      this.inputValues[index] += amount;
    },
    clearValue(index) {
      this.inputValues[index] = 0;
    }
  }
};
</script>



<template>
  <div class="page-container">
    <!-- input box-->
    <div class="grid-container">
        <!-- Input box grid -->
        <div class="input-box">
          <input type="text" v-model="inputValues[0]" readonly/>
          <div class="button-container">
            <button @click="addValue(0, 10000)">+10000</button>
            <button @click="addValue(0, 5000)">+5000</button>
            <button @click="addValue(0, 2000)">+2000</button>
            <button @click="clearValue(0)">Clear</button>
          </div>
        </div>
        <div class="input-box">
          <input type="text" v-model="inputValues[1]" readonly/>
          <div class="button-container"> 
            <button @click="addValue(1, 10000)">+10000</button>
            <button @click="addValue(1, 5000)">+5000</button>
            <button @click="addValue(1, 2000)">+2000</button>
            <button @click="clearValue(1)">Clear</button>
          </div>
        </div>
        <div class="input-box">
          <input type="text" v-model="inputValues[2]" readonly/>
          <div class="button-container">
            <button @click="addValue(2, 10000)">+10000</button>
            <button @click="addValue(2, 5000)">+5000</button>
            <button @click="addValue(2, 2000)">+2000</button>
            <button @click="clearValue(2)">Clear</button>
          </div>
        </div>
        <div class="input-box">
          <input type="text" v-model="inputValues[3]" readonly/>
          <div class="button-container">
            <button @click="addValue(3, 10000)">+10000</button>
            <button @click="addValue(3, 5000)">+5000</button>
            <button @click="addValue(3, 2000)">+2000</button>
            <button @click="clearValue(3)">Clear</button>
          </div>
        </div>
        <div class="input-box">
          <input type="text" v-model="inputValues[4]" readonly/>
          <div class="button-container">
            <button @click="addValue(4, 10000)">+10000</button>
            <button @click="addValue(4, 5000)">+5000</button>
            <button @click="addValue(4, 2000)">+2000</button>
            <button @click="clearValue(4)">Clear</button>
          </div>
        </div>
        <div class="input-box">
          <input type="text" v-model="inputValues[5]" readonly/>
          <div class="button-container">
            <button @click="addValue(5, 10000)">+10000</button>
            <button @click="addValue(5, 5000)">+5000</button>
            <button @click="addValue(5, 2000)">+2000</button>
            <button @click="clearValue(5)">Clear</button>
          </div>
        </div>
        <button class="top-right-button" @click="end_turn">End Turn</button>
    </div>
  </div>
  
</template>



<style>
    .page-container {
      min-height: 100vh; /* Set the minimum height to fill the viewport */
      display: flex;
      align-items: center;
      justify-content: center;
      background-image: url('../assets/bg.png');
      background-size: cover;
      background-position: center;
    }

.background-image {
  width: auto;
  height: 100%;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-row-gap: 300px; 
  grid-column-gap: 50px; /* Gap between rows */
  /* gap: 10px; Gap between columns */
  margin-top: 180px;
}

.input-box {
  padding: 5px;
  border: 5px solid #ccc;
  border-radius: 20px;
}

/* Additional styling for the input boxes */
.input-box input {
  width: 100%;
  border: none;
  outline: none;
  text-align: center;
  font-size: 20px;
}

.top-right-button {
  position: absolute;
  top: 20px;
  right: 20px;
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  z-index: 2; /* Ensure the button appears above the image */
}

.button-container {
  display: flex;
  justify-content: center;
  margin-top: 10px; /* Adjust the gap between the input and button as needed */
}

/* Style for the buttons */
.button-container button {
  margin: 0 2px; /* Adjust the left and right margin to create even gaps between buttons */
  font-size: 20px;
}
  </style>
