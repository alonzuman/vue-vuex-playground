<template>
  <div>
    <h3>Add Todo</h3>
    <form @submit="onSubmit">
      <input v-model="title" type="text" required placeholder="Do my laundry" />
      <button value="submit" type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style>
form {
  max-width: 350px;
  margin: 0 auto;
}

button {
  width: 100%;
  margin: 8px 0px;
  padding: 8px 16px;
  border-radius: 4px;
}

input {
  width: 100%;
  padding: 8px 16px;
  font-size: 16px;
  border-radius: 4px;
  border: 1px solid #00000015;
}

button,
input:focus {
  outline: none;
}
</style>