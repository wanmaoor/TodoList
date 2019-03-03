<template>
  <div class="container">
    <form @submit="addItem">
      <div class="form-row form">
        <div class="col-sm-9 my-2 ">
          <label class="sr-only" for="inlineFormInputName">Name</label>
          <input type="text" v-model="item" class="form-control" id="inlineFormInputName" placeholder="添加事件清单">
        </div>
        <div class="col-sm-1 my-2">
          <button type="submit" class="btn btn-primary">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<style>

  .form{
    display: flex;
    justify-content: center;
    margin: auto;
  }
</style>


<script>
import uuid from 'uuid';
export default {
  name: "AddTodoList",
  data(){
    return {
      item: ''
    }
  },
  methods: {
    addItem(e){
      const newItem = {
        id: uuid.v4(),
        item: this.item,
        isCompleted: false
      }
      if (this.item !== '') {
        this.$emit('add-item', newItem)
        this.item =''
      }else{
        alert('请输入待办事件')
      }
      e.preventDefault();
    }
  },
};
</script>

