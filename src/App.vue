<template>
  <div id="app" class="container">
    
      <div class="col-md-4 offset-md-4">
        <search-bar @termeChange="onTermeChange" ></search-bar>
      </div>
      <div class="row">
        <div class="col-md-4">
          <VideoDetail :video="selectedVideo"></VideoDetail>
        </div>
        <div class="col-md-8">
          <video-list :videoArray="videos" @videoSelectt="onVideoSelect2"></video-list>
        </div>
      </div>
         
            
      
    
    
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';
const API_KEY="AIzaSyB5nDj6PppA8LCvwRQcFx6qaSQn0SvZz0A";
import axios from 'axios';
export default {
  name: 'app',
  components:{
    SearchBar,
    VideoList,
    VideoDetail  
  },
  data(){
    return {
      videos:[],
      selectedVideo:null
      
    };
  },
  
  methods:{
    onTermeChange (searchTerm){
      axios.get('https://www.googleapis.com/youtube/v3/search',{
        params:{
          key: API_KEY,
          type:'video',
          part:'snippet',
          q:searchTerm,
          maxResults:25
        }
      }).then(response => {
        this.videos=response.data.items;
      });
    },
    onVideoSelect2(vid){
      this.selectedVideo=vid;
    }
  }
  
  
}
</script>

<style></style>