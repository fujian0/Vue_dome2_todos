<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <TodoHeader :addTodo="addTodo" />
        <TodoMain :todos="todos" :deleteTodo="deleteTodo"/>
        <TodoFooter :todos="todos" :selectAll="selectAll" :deleteComputed="deleteComputed"/>
      </div>
    </div>
  </div>
</template>

<script>
  import Header from './components/Header'
  import Footer from './components/Footer'
  import Main from './components/Main'
    export default {
    data () {
      return {
        todos: [
          {title:'吃饭',completed:false},
          {title:'睡觉',completed:false},
          {title:'敲代码',completed:true}
        ]
      }
    },
      methods: {
      //添加todo
      addTodo (todo){
        this.todos.unshift(todo)
      },
        //删除todo
        deleteTodo (index) {
        this.todos. splice(index,1)
        },
        //全选或者全不选
        selectAll(check){
          this.todos.forEach(todo =>todo.completed = check)
        },
        //删除完成的
        deleteComputed (){
        //过滤产生新的数组并更新
       this.todos = this.todos.filter(todo=>!todo.completed)
        }
      },
       components:{
         TodoHeader: Header,
         TodoMain: Main,
         TodoFooter: Footer
       }

    }
</script>

<style>
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
