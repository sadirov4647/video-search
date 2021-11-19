<template>
        <li class="list-group-item" @click="onVideoClick">
            <!-- <img :src="thumbnailUrl"> -->
            <!-- {{ response.snippet.title }} -->
        </li>
</template>

<script>
    export default {
        name:'VideoListItem',
        props:['response'],
        computed:{
            // thumbnailUrl(){
            //     return this.response.snippet.thumbnails.default.url
            // }
        },
        methods:{
            onVideoClick(){
                this.$emit('videoItemClicked', this.response)
            }
        }
    }
</script>

<style scoped>
    li{
        display: flex;
        cursor: pointer;
    }
    li:hover{
        background-color: #eee;
    }
</style>