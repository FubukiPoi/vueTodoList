<template>
<div>
    <li>{{content}}<button @click="handleDelete()">delete</button></li>
    
</div>
</template>

<script>
export default {
  props: ["content", "index"],
  methods: {
    handleDelete() {
      //this.$emit()与父组件通信
      this.$emit("delete", this.index);
    }
  }
};
</script>

<style>
li {
  list-style-type: none;
}
</style>
