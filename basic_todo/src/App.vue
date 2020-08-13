<template>
  <div id="app" class="container">
    <h1 class="text-center">To do app</h1>
    <CompletedTodo />
    <AddTodo />
    <hr />
    <TodoList />
    <UserList />
  </div>
</template>

<script>
// import Todo from "@/components/Todo.vue"
import TodoList from "@/components/TodoList.vue"
import AddTodo from "@/components/AddTodo.vue"
import CompletedTodo from "@/components/CompletedTodo.vue"
import UserList from "./components/UserList.vue"

export default {
  components: {
    TodoList,
    AddTodo,
    CompletedTodo,
    UserList,
  },
  data() {
    return {
      todoText: "",
    }
  },

  methods: {
    // addTodo(value) {
    //   this.todos.push({
    //     id: Math.random(),
    //     text: value,
    //     checked: false,
    //   })
    //   this.todoText = ""
    // },
    // toggleCheckbox({ id, checked }) {
    //   console.log(id, checked)
    //   const index = this.todos.findIndex((todo) => {
    //     return todo.id === id
    //   })
    //   this.todos[index].checked = checked
    // },
    // deleteTodo(id) {
    //   // option 1
    //   // const index = this.todos.findIndex((todo) => {
    //   //   return todo.id === id
    //   // })
    //   // this.todos.splice(index, 1)
    //   //option2
    //   this.todos = this.todos.filter((todo) => todo.id !== id)
    // },
  },
}
</script>

<style></style>
