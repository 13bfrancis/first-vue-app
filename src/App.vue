<template>
  <div class="container">
    <app-header>To Do App</app-header>
    <add-item @addedItem="addItem"></add-item>
    <to-dos @removedItem="removeItem" :items="items"></to-dos>
  </div>
</template>

<script>
import ToDosVue from "./components/ToDos.vue";
import HeaderVue from "./components/Header.vue";
import AddItemVue from "./components/AddItem.vue";

export default {
  name: "app",
  components: {
    ToDos: ToDosVue,
    appHeader: HeaderVue,
    addItem: AddItemVue
  },
  data() {
    return {
      items: [],
      itemInput: ""
    };
  },
  methods: {
    addItem(itemText) {
      this.items.push(itemText);
    },
    removeItem(index) {
      this.items.splice(index, 1);
    }
  }
};
</script>

<style>
:root {
  font-family: "Open Sans", sans-serif;
}
.container {
  position: relative;
  max-width: 500px;
}
@media screen and (min-width: 500px) {
  .container {
    left: calc((100% - 500px) / 2);
  }
}
</style>
