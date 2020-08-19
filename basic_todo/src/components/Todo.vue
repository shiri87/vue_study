<template>
  <div class="mb-2 d-flex">
    <div>
      <input type="checkbox" :checked="todo.checked" @change="toggleCheckbox" />
    </div>
    <span
      class="ml-3 flex-grow-1"
      :class="todo.checked && 'text-muted'"
      :style="todo.checked && 'text-decoration:line-through'"
    >{{ todo.text }}</span>
    <!--     
      :class="todo.checked ? 'text-muted':''"
      :style="todo.checked ?'text-decoration:line-through':''"
    -->
    <div class="btn btn-danger btn-sm" @click="clickDelete">Delete</div>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  computed: {
    // todos() {
    //   return this.$store.state.todos
    // },
    numberOfCompletedTodo() {
      // return this.todos.filter((todo) => todo.checked).length
      return this.$store.getters["todo/numberOfCompletedTodo"];
    },
  },
  methods: {
    toggleCheckbox(e) {
      this.$store.dispatch("todo/toggleTodo", {
        //action mode
        id: this.todo.id,
        checked: e.target.checked,
      });
      // this.$store.commit("TOGGLE_TODO", { //mutation mode

      // this.$emit("toggle-checkbox", {
      //   // id: this.todo.id,
      //   // checked: e.target.checked,
      //   id: this.todo.id,
      //   checked: e.target.checked,
      // })
    },
    clickDelete() {
      // this.$store.commit("DELETE_TODO", this.todo.Id) //mutation mode

      this.$store.dispatch("todo/deleteTodo", this.todo.Id); //action mode

      // this.$emit("click-delete", this.todo.id)
    },
  },
};
</script>

<style></style>
