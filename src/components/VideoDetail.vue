<template>
    <div class="video-detail__wrapper" v-if="response">
        <div class="video-details">
            <div class="embed-responsive embed-responsive-16by9">
                <iframe class="embed-responsive-item" :src="videoUrl" frameborder="0"></iframe>
            </div>
            <div class="details">
                {{ response.snippet.title }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:'VideoDetail',
        props:['response'],
        computed:{
            videoUrl(){
                const videoId = this.response.id.videoId;
                return `https://www.youtube.com/embed/${videoId}`
            }
        }
    }
</script>

<style scoped>
    .video-details{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .video-detail__wrapper{
        display: flex;
        justify-content: center;
        margin-bottom: 32px;
        margin-top: 32px;
    }
</style>