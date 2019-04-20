<template>
  <ul v-if="items.length !== 0">
    <li @click="clicked(index)" v-for="(item, index) in items" :key="index">
      {{ item }}
    </li>
  </ul>
</template>

<script>
export default {
  props: ["items"],
  methods: {
    clicked(i) {
      this.$emit("removedItem", i);
    }
  }
};
</script>

<style scoped>
ul {
  width: 100%;
  box-sizing: border-box;
  border: 1px solid black;
  padding: 20px;
  margin-top: 0;
  list-style: none;
  text-align: center;
}
li {
  margin-bottom: 10px;
  transition: color linear 0.3s;
  cursor: pointer;
}
li:last-child {
  margin-bottom: 0;
}
li:hover {
  color: red;
}
</style>
