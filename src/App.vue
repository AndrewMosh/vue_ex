<template>
  <div>
    <Bitch></Bitch>
    <Counter></Counter>
    <ToDoList></ToDoList>
  </div>
</template>

<script>
import Bitch from "./components/Bitch.vue";
import Counter from "./components/Counter.vue";
import ToDoList from "./components/ToDoList.vue";

export default {
  name: "App",
  components: {
    Bitch,
    Counter,
    ToDoList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
