<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <header-list :addTodo="addTodo"/>
        <main-list :todos="todos" :changeDone="changeDone" :deleteTods="deleteTods"/>
        <footer-list :todos="todos" :checkAllTodo="checkAllTodo" :clearAll="clearAll"/>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderList from "./components/HeaderList";
import MainList from "./components/MainList";
import FooterList from "./components/FooterList";

export default {
  name: 'App',
  components: {
    HeaderList,
    MainList,
    FooterList
  },
  data () {
    return {
      todos: [
        {'id':'001',title: '老王', done: true},
        {'id':'002',title: '卢老师', done: true},
        {'id':'003',title: '温哥', done: false}
      ]
    }
  },
  methods: {
    // 添加todo
    addTodo(todoObj){
      this.todos.unshift(todoObj)
    },
    // 勾选状态切换
    changeDone(id){
      this.todos.forEach((todo) => {
        if (todo.id == id) {
          todo.done = !todo.done
        }
      })
    },
    // 删除todo
    deleteTods(id){
      this.todos = this.todos.filter( todo => todo.id !== id )
    },
    // 全选or取消全选
    checkAllTodo(done){
      this.todos.forEach(todo => todo.done = done )
    },
    clearAll(){
      this.todos = this.todos.filter( todo => !todo.done  )
    }
  }
}
</script>

<style>
/*base*/
body {
  background: #fff;
}
.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}
.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}
.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}
.btn:focus {
  outline: none;
}
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
