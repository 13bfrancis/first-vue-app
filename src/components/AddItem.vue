<template>
  <div class="container">
    <input type="text" v-model="itemText" />
    <button @click="clicked">Add Item</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      itemText: ""
    };
  },
  methods: {
    clicked() {
      this.$emit("addedItem", this.itemText);
      this.itemText = "";
    }
  }
};
</script>

<style scoped>
input[type="text"] {
  padding-left: 5px;
  width: 100%;
  box-sizing: border-box;
  font-size: 1.5rem;
}
button {
  width: 100%;
  font-size: 25px;
  margin: 10px 0;
  background: none;
  outline: none;
  border: none;
  box-shadow: 2px 2px 7px rgba(0, 0, 0, 0.3);
  padding: 10px;
  background: greenyellow;
  box-sizing: border-box;
  transition: background linear 0.3s;
  cursor: pointer;
}
button:hover,
button:active {
  background: rgba(172, 255, 47, 0.589);
}
.container {
  border: 1px solid black;
  padding: 20px;
}
</style>
