<template>
    <ul class="todos">

        <li class="card" draggable="true">
            <div class="cb-container">
                <input @click="changeStatus" type="checkbox" :checked="todo.isComplete" class="cb-input" />
                <span class="check"></span>
            </div>
            <p class="item">
                <del v-if="todo.isComplete"> {{todo.title}}</del>
                <span v-else> {{todo.title}}</span> 
            </p>
            <button @click="deleteTodo" class="clear">
                <img src="../assets/images/icon-cross.svg" alt="Clear it" />
            </button>
        </li>



 
    </ul>
</template>

<script>
export default {
props:{
    todo:Object
},
methods: {
    deleteTodo(){
        if(confirm("واقعا؟!"))
        {this.$emit("Delete",this.todo.id);}

    },
    changeStatus()
    {

        this.$emit("changeStatus",this.todo.id,!this.todo.isComplete);
    }
    
},
}
</script>

<style></style>