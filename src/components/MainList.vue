<template>
  <ul class="todo-main">
    <item-list 
    v-for="todoObj in todos" 
    :key="todoObj.id"
    :todo="todoObj"
    :changeDone="changeDone"
    :deleteTods="deleteTods"
    />
  </ul>
</template>

<script>
import ItemList from "./ItemList";
export default {
  name: 'MainList',
  components: { ItemList },
  props: ['todos','changeDone','deleteTods']
}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
