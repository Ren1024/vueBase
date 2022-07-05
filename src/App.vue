<template>
      <div>
        <Header></Header>
        <div class="container">
            <Add :addComment="addComment"></Add>
            <List :comments="comments" :deleteComment="deleteComment"></List>
        </div>
    </div>
</template>

<script>
    import Header from '@/components/Header.vue'
    import Add from './components/Add.vue'
    import List from './components/List.vue'
    export default{
        name:'',
        components:{
            Header,
            Add,
            List,
        },
        data(){
            return {
                comments:[
                    {id:1, name:'刘德华', comment:'我不是笨小孩！'},
                    {id:2, name:'张学友', comment:'我和你吻别，在无情的夜！'},
                    {id:3, name:'渣渣辉', comment:'是兄弟就来砍我！'},
                ]
            }
        },
        methods:{
            addComment(comment){
                this.comments.unshift(comment)
            },
            deleteComment(index){
                this.comments.splice(index,1)
            }
        }
    }
</script>

<style>

</style>