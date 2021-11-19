<template>
      <ul>
        <VideoListItem
        class="list-group"
        v-for="response in responses"
        :response="response"
        :key="response.etag"
        @videoItemClicked="onVideoClick"
        />
        <VideoListItem/>
      </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue';
export default {
    name:'VideoList',
    components:{
      VideoListItem
    },
    props:['responses'],
    methods:{
      onVideoClick(response){
        this.$emit('videoItemClicked', response)
      }
    }
};
</script>

<style scoped>
</style>
