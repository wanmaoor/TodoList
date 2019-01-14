<template>
  <div id="app" class="container">
    <Header></Header>
    <AddTodoList @add-item="addItem"></AddTodoList>
    <TodoList :todos="todos" @remove-item="removeItem"></TodoList>
  </div>
</template>

<script>
import Header from "./components/Header";
import TodoList from "./components/TodoList";
import AddTodoList from './components/AddTodoList';
export default {
  name: "app",
  components: {
    Header,
    TodoList,
    AddTodoList
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    removeItem(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addItem(item){
      this.todos.push(item)
    }
    
    
  }
};
</script>

<style>
body{
  background: #f4f4f4 !important
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
 
}
</style>
