<template>
<div class="todo-container">
    <div class="todo-wrap">
        <HeaderVue></HeaderVue>
        <ListVue></ListVue>
        <FooterVue></FooterVue>

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