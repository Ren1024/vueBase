<template>
      <div class="col-md-8">
        <h3 class="reply">评论回复：</h3>
        <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
        <ul class="list-group">
            <ItemVue 
                v-for="(comment, index) in comments" 
                :key="comment.id" 
                :comment="comment"
                :deleteComment="deleteComment"
                :index="index"
            ></ItemVue>
        </ul>
      </div>
</template>

<script>
    import ItemVue from './Item.vue'
    export default {
        name:'',
        components:{
            ItemVue,
        },
        props:['comments','deleteComment'],
    }
</script>

<style>
.reply {
  margin-top: 0px;
}
</style>