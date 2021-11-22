<template>
    <div v-if="response">
        <div class="embed-responsive embed-responsive-16by9">
            <iframe class="embed-responsive-item" :src="videoUrl" frameborder="0"></iframe>
        </div>
        <div class="details">
            {{ response.snippet.title }}
        </div>
    </div>
</template>

<script>
    export default {
        name:'VideoDetail',
        props:['response'],
        computed:{
            videoUrl(){
                const {videoId} = this.video.id;
                return `https://www.youtube.com/embed/${videoId}`
            }
        }
    }
</script>

<style scoped>

</style>