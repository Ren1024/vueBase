<template>
    <div class="todo-container">
        <div class="todo-wrap">
            <!-- props -->
            <!-- <HeaderVue :addTodo="addTodo"></HeaderVue> -->
            <!-- 自定义事件 -->
            <HeaderVue @addTodo="addTodo"></HeaderVue>
            <ListVue :todos="todos" :updateOne="updateOne" :deleteOne="deleteOne"></ListVue>
            <FooterVue :todos="todos" :updateAll="updateAll" :deleteAll="deleteAll"></FooterVue>
        </div>
    </div>
</template>

<script>
import HeaderVue from './components/Header.vue'
import ListVue from './components/List.vue'
import FooterVue from './components/Footer.vue'

export default {
    name:'',
    components:{
        HeaderVue,
        ListVue,
        FooterVue
    },
    data(){
        return {
            todos: JSON.parse(localStorage.getItem('TODOS_KEY')) || []
        }
    },
    watch:{
        todos:{
            deep:true,
            handler(newVal, oldVal){
                // console.log('@@');
                localStorage.setItem('TODOS_KEY',JSON.stringify(newVal))
            }
        }
    },
    methods:{
        addTodo(todo){
            this.todos.unshift(todo)
        },
        updateOne(index){
            this.todos[index].isOver = !this.todos[index].isOver
        },
        deleteOne(index){
            this.todos.splice(index,1)
        },
        updateAll(val){
            this.todos.forEach(item => item.isOver = val)
        },
        deleteAll(){
            // 删选出来没选中的，然后赋值
            this.todos = this.todos.filter(item => !item.isOver)
        }
    }
}
</script>

<style>
/*app*/
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