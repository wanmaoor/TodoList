<template>
  <div class="container">
    <div class="alert alert-primary show" role="alert" v-for="todo in todos" :key="todo.id">
      <span>{{todo.item}}</span>
      <button type="button" class="btn btn-danger" @click="$emit('remove-item', todo.id)">删除</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "TodoList",
  props: ["todos"]
};
</script>
<style scoped>
  .show{
    display: flex;
  }
  .show span{
    flex: 10;
    font-size: 1.2rem;
  }
  .show button{
    flex: 1
  }
</style>



