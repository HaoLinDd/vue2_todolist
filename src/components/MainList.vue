<template>
  <ul class="todo-main">
    <item-list/>
    <item-list/>
    <item-list/>
  </ul>
</template>

<script>
import ItemList from "./ItemList";
export default {
  name: 'MainList',
  components: { ItemList },
  props: {
    
  }
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
