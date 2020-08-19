<template>
  <input
    type="text"
    class="w-100 p-2"
    placeholder="Type Todol list"
    v-model="todoText"
    @keyup.enter="addTodo"
  />
</template>

<script>
export default {
  data() {
    return { todoText: "" };
  },
  methods: {
    addTodo(e) {
      // this.$emit("add-todo", e.target.value)

      //this.$store.commit("ADD_TODO", e.target.value) // mutation mode
      this.$store.dispatch("todo/addTodo", e.target.value); //action mode

      this.todoText = "";
    },
  },
};
</script>

<style></style>
