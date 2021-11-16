<template>
  <div class="root">
    <div class="number-button" @click="counterMinus">-</div>
    <input type="number" v-model="number" @input="inputValidation" />
    <div class="number-button" @click="counterPlus">+</div>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      number: 0,
      maxValue: 10,
      minValue: 0,
    };
  },
  methods: {
    inputValidation() {
      if(this.number > this.maxValue) {
        this.number = this.maxValue
      } else if (this.number < this.minValue) {
        this.number = this.minValue
      } else if (this.number === "") {
        this.number = this.minValue
      }
    },
    counterPlus() {
      if (this.number < this.maxValue) {
        this.number++;
      }
    },
    counterMinus() {
      if (this.number > this.minValue) {
        this.number--;
      }
    },
  },
};
</script>
<style>
.root {
  display: flex;
}
.number-button {
  padding: 0px 10px;
  background: #ededed;
  cursor: pointer;
}
input {
  width: 40px;
  border: 1px solid gainsboro;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
input[type=number] {
  -moz-appearance:textfield;
}
</style>
