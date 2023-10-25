<template>
  <body>
    <AppHeader></AppHeader>

    <main>
      <AddToDo @AddNewTodo="AddToDo"></AddToDo>
      <Todo v-for=" todo  in todos" :key="todo.id" :todo="todo" @Delete="DeleteTodo" @changeStatus="changeTodostatus" ></Todo>
      <div class="card stat">
        <p class="corner"><span id="items-left">0</span> مورد باقی مانده</p>
        <div class="filter">
          <button id="all" class="on">همه</button>
          <button id="active">فعال</button>
          <button id="completed">تکمیل</button>
        </div>
        <div class="corner">
          <button @click="deleteCompleted" id="clear-completed">حذف تکمیل شده ها</button>
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
      todos:[ ]
    }
  },
  methods: {
    AddToDo(todoTitle){
      const uuid=Math.random().toString(16).slice(2);
      const newTodo={title:todoTitle,isComplete:false,id:uuid};
       this.todos.push(newTodo);
       console.log(todoTitle);
    },
    DeleteTodo(todoId){
      this.todos= this.todos.filter(t=>t.id!=todoId);
    },
    changeTodostatus(todoId,newStatus){
       var newTodos=[...this.todos];
       var item=newTodos.find(i=>i.id==todoId);
       item.isComplete=newStatus;
       this.todos=newTodos;
       
    },
    deleteCompleted(){
      if(confirm("تکیل ها  حذف شوند؟؟؟"))
       {var newTodos=[...this.todos];
         newTodos=newTodos.filter(i=>i.isComplete==false); 
       this.todos=newTodos;}
       
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
