<template>
  <div>
      <SearchBar  @termChange="onTermChange"/>
      <VideoDetail :response="selectedVideo"/>
      <VideoList @videoItemClicked="onVideoClick" :response="responses"/>
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar'
import VideoList from './components/VideoList'
import VideoDetail from './components/VideoDetail'
const API_KEY = 'AIzaSyBc9yFPBOk5A_KM8pRJo_njiLtDGmQb36E';
export default {
    name: 'App',
    data(){
      return{
        responses: [],
        selectedVideo: null
      }
    },
    components:{
     SearchBar,
     VideoList,
     VideoDetail
    },
    methods:{
      onVideoClick(response){
        this.selectedVideo = response
      },
      onTermChange: function(searchTerm){
      axios.get('https://www.googleapis.com/youtube/v3/search',{
        params:{
        key: API_KEY,
        type:'video',
        part:'snippet',
        q:searchTerm
      }
      }).then(response => this.responses = response.data.items)
      }
    }
};
</script>

<style scoped>

</style>
