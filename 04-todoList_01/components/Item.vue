<template>
   <li @mouseenter="isShow = true" @mouseleave="isShow = false" :class="{mybgc : isShow}">
        <label>
            <input type="checkbox" :checked="todo.isOver" @click="updateO"/>
            <!-- <input type="checkbox" v-model="isChecked" @click="updateO"/> -->
            <span>{{todo.content}}</span>
        </label>
        <button class="btn btn-danger" v-show="isShow" @click="deleteO">删除</button>
    </li>
</template>

<script>
export default {
    name:'',
    props:{
        // props第二种用法，限定接受类型
        todo:Object,
        updateOne:Function,
        index:{
          type:Number,
          required:true
        },
        deleteOne:Function
    },
    // computed:{
    //     isChecked:{
    //         get(){
    //             return this.todo.isOver
    //         },
    //         set(){

    //         }
    //     }
    // },
    data(){
        return {
            isShow:false
        }
    },
    methods:{
        updateO(){
          this.updateOne(this.index)
        },
        deleteO(){
          this.deleteOne(this.index)
        }
    }
}
</script>

<style>
.mybgc {
    background-color: #eee;
}

/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
</style>