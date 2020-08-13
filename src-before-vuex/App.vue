<template>
  <div id="app" class="container">
    <h1 class="text-center">To do app</h1>
    <CompletedTodo :todos="todos" />
    <!-- <input
      type="text"
      class="w-100 p-2"
      placeholder="Type Todol list"
      v-model="todoText"
      @keyup.enter="addTodo"
    />-->
    <AddTodo @add-todo="addTodo" />
    <hr />
    <TodoList :todos="todos" @toggle-checkbox="toggleCheckbox" @click-delete="deleteTodo" />
    <!-- <Todo
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @toggle-checkbox="toggleCheckbox"
      @click-delete="deleteTodo"
    />-->
  </div>
</template>

<script>
// import Todo from "@/components/Todo.vue"
import TodoList from "@/components/TodoList.vue";
import AddTodo from "@/components/AddTodo.vue";
import CompletedTodo from "@/components/CompletedTodo.vue";

export default {
  components: {
    TodoList,
    AddTodo,
    CompletedTodo,
  },
  data() {
    return {
      todoText: "",
      todos: [
        { id: 1, text: "buy a car", checked: false },
        { id: 2, text: "buy some panties", checked: false },
      ],
    };
  },

  methods: {
    addTodo(value) {
      // console.log(e.target.value);
      this.todos.push({
        id: Math.random(),
        text: value,
        checked: false,
      });
      this.todoText = "";
    },
    toggleCheckbox({ id, checked }) {
      console.log(id, checked);
      const index = this.todos.findIndex((todo) => {
        return todo.id === id;
      });
      this.todos[index].checked = checked;
    },
    deleteTodo(id) {
      // option 1
      // const index = this.todos.findIndex((todo) => {
      //   return todo.id === id
      // })
      // this.todos.splice(index, 1)
      //option2
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style></style>
