<template>
  <div id="todolist">
    <input v-model="inputValue"/>
    <button @click="handleSubmit">submit</button>
    <ul>
      <todo-item 
      v-for="(item,index) of list" 
      :key="index"
      :content="item" 
      :index="index" 
      @delete="handleDelete">
      </todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem";

export default {
  components: {
    "todo-item": TodoItem
  },
  data() {
    return {
      inputValue: "",
      list: []
    };
  },
  methods: {
    handleSubmit() {
      this.list.push(this.inputValue);
      this.inputValue = "";
    },
    handleDelete(){
      this.list.splice(this.index,1);
    }
  }
};
</script>

<style>
#todolist {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
