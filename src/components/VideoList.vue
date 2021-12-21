<template>
  <ul class="video-list__list" v-if="responses">
  <VideoListItem
    v-for="response in responses"
    :response="response"
    :key="response.etag"
    @videoItemClicked="onVideoClick"
  />
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
.video-list__list{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  padding: 0;
  margin: 0;
}
</style>
