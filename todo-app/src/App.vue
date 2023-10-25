<template>
  <body>
    <AppHeader></AppHeader>

    <main>
      <AddToDo @AddNewTodo="AddToDo"></AddToDo>
      <Todo v-for="(todo,index) in todos" :key="index" :todo="todo" ></Todo>
      <div class="card stat">
        <p class="corner"><span id="items-left">0</span> مورد باقی مانده</p>
        <div class="filter">
          <button id="all" class="on">همه</button>
          <button id="active">فعال</button>
          <button id="completed">تکمیل</button>
        </div>
        <div class="corner">
          <button id="clear-completed">حذف تکمیل شده ها</button>
        </div>
      </div>
    </main>
    <AppFooter></AppFooter>
  </body>
 
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AddToDo from './components/AddToDo.vue';
import Todo from './components/Todo.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AddToDo,
    Todo,
    AppFooter
  },
  data() {
    return {
      todos:[
        {title:"دیدن آموزش vue",isComplete:false},
        {title:"دیدن آموزش asp.net Core",isComplete:true}
    ]
    }
  },
  methods: {
    AddToDo(todoTitle){
      console.log(todoTitle);
      const newTodo={title:todoTitle,isComplete:false};
       this.todos.push(newTodo);
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
