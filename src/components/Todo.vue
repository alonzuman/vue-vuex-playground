<template>
  <li class="todo">
    <p>{{todo.title}}</p>
    <div>
      <i @click="deleteTodo(todo.id)" class="fas fa-times-circle"></i>
    </div>
  </li>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "Todo",
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    ...mapActions(["deleteTodo"])
  }
};
</script>

<style>
.todo {
  border-radius: 4px;
  padding: 1rem;
  border: 1px solid #00000015;
  text-align: center;
  display: flex;
  justify-content: space-between;
}

i {
}

i:hover {
  cursor: pointer;
}
</style>