<template>
    <div>
        <h2>hello word</h2>
        <button @click="count++">点击了{{count}}次</button>
    </div>
</template>

<script>
    export default {
        name:'',
        data(){
            return {
                count:0
            }
        }
    }
</script>

<style>
    h2 {
        color: pink;
    }
</style>