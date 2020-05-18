<template>
  <div>
    <h3>Todos</h3>
    <ul class="todos">
      <Todo :key="todo.id" v-for="todo in allTodos" class="todo" :todo="todo"></Todo>
    </ul>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
import Todo from "./Todo";

export default {
  name: "Todos",
  methods: { ...mapActions(["fetchTodos"]) },
  components: { Todo },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
};
</script>

<style>
.todos {
  display: grid;
  gap: 1rem;
  grid-template-columns: 1fr 1fr 1fr;
}

@media only screen and (max-width: 768px) {
  .todos {
    grid-template-columns: 1fr;
  }
}
</style>