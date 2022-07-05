<template>
    <div class="col-md-4">
        <form class="form-horizontal">
        <div class="form-group">
            <label>用户名</label>
            <input type="text" class="form-control" placeholder="用户名" v-model="name">
        </div>
        <div class="form-group">
            <label>评论内容</label>
            <textarea 
                class="form-control" 
                rows="6" 
                placeholder="评论内容"
                v-model="comment"
            ></textarea>
        </div>
        <div class="form-group">
            <div class="col-sm-offset-2 col-sm-10">
            <button type="button" class="btn btn-default pull-right" @click="addC">提交</button>
            </div>
        </div>
        </form>
    </div>
</template>

<script>
    export default {
        name:'',
        data(){
            return {
                name:'',
                comment:'',
            }
        },
        props:['addComment'],
        methods:{
            addC(){
                // 获取用户输入数据
                let {name,comment} = this
                let id = Date.now()
                // 生成数据对象
                if(name.trim() && comment.trim()){
                    let obj = {
                        id,
                        name,
                        comment
                    }
                    // 添加到comments数据中
                    this.addComment(obj)
                }else {
                    alert('请输入合法的用户名和评论！')
                }
                this.name = '',
                this.comment = ''
                
            }
        }
    }
</script>

<style>
</style>