<template>
    <ul class="todo-main">
        <ItemVue 
            v-for="(todo, index) in todos" 
            :key="todo.id" 
            :todo="todo"
            :updateOne="updateOne"
            :index="index"
            :deleteOne="deleteOne"
        ></ItemVue>
    </ul>
</template>

<script>
import ItemVue from './Item.vue'

export default {
    name:'',
    components:{
        ItemVue
    },
    props:['todos', 'updateOne', 'deleteOne'],
}
</script>

<style>
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