<template>
  <div class="container">
    <AddTodo />
    <Todos />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "App",
  components: {
    Todos,
    AddTodo
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  max-width: 1024px;
  margin: 0 auto;
  overflow: auto;
  padding: 0 2rem;
  padding-bottom: 60px;
}

li {
  list-style: none;
}
</style>
