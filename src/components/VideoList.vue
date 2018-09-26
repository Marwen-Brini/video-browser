<template>
	
		<ul class="list-unstyled">
			<videoListItem v-for="vi in videoArray" :item="vi" @videoSelect="onVideoSelect2"></videoListItem>
		</ul>	
	
	
	<!--<ul>
		first approach
		<li v-for="vi in videoArray"><img :src="vi.snippet.thumbnails.default.url"><a :href="'https://youtube.com/watch?v='+vi.id.videoId">{{vi.snippet.title}}</a></li>-->
		<!--<img :src="vi.snippet.thumbnails.default.url">{{vi.snippet.title}}
	</ul>-->
</template>

<script>
	import VidItem from './videoItemList';
	export default {
		name:'VideoList',
		props:{
			videoArray : Array
		},
		components:{
			videoListItem:VidItem
		},
		data(){
			return {
				item:''
			};
		},
		methods:{
			onVideoSelect2(item){
				this.$emit('videoSelectt',item);
				
			}
		}
	}
</script>

<style>
	
</style>