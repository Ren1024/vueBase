<template>
    <div>
        <HeaderVue></HeaderVue>
        <div class="container">
            <!-- <AddVue :addComment="addComment"></AddVue> -->
            <!-- <AddVue ref="aa"></AddVue> -->
            <AddVue @addC="addComment"></AddVue>
            <ListVue :comments="comments" :deleteComment="deleteComment"></ListVue>
        </div>
    </div>
</template>

<script>
    import HeaderVue from './components/Header.vue' 
    import AddVue from './components/Add.vue'
    import ListVue from './components/List.vue'

    export default {
        name:'',
        data(){
            return {
                comments:[
                    {id:1, username:'刘德华', content:'我不是笨小孩'},
                    {id:2, username:'张学友', content:'冷冷的冰雨在脸上拍'},
                    {id:3, username:'渣渣辉', content:'是兄弟就来砍我'},
                ]
            }
        },
        components: {
            HeaderVue,
            AddVue,
            ListVue,
        },
        methods:{
            addComment(comment){
                this.comments.unshift(comment)
            },
            deleteComment(index){
                this.comments.splice(index,1)
            }
        },
        mounted(){
            this.$refs.aa.$on('addComment',this.addComment)
        }
    }
</script>

<style>

</style>