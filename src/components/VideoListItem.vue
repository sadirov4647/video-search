<template>
        <li class="list-group-item" @click="onVideoClick">
            <img :src="thumbnailUrl">
            <h2>{{ titleUrl }}</h2>
        </li>
</template>

<script>
    export default {
        name:'VideoListItem',
        props:['response'],
        computed:{
            thumbnailUrl(){
                return this.response.snippet.thumbnails.default.url
            },
            titleUrl(){
                return this.response.snippet.title
            }
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