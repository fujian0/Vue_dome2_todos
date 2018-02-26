<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <TodoHeader/>
        <TodoFooter/>
        <TodoMain :todos="todos"/>
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
       components:{
         TodoHeader: Header,
         TodoFooter: Footer,
         TodoMain: Main
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
