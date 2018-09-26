<template>
	
		<li class="media my-4 list-group-item" @click="onVideoSelect">
			<a :href="'https://youtube.com/watch?v='+item.id.videoId">
			  	<img class="mr-3 rounded" :src="item.snippet.thumbnails.medium.url">
			</a>
			<div class="media-body">
				<h5 class="mt-0 mb-1">
				    <a :href="'https://youtube.com/watch?v='+item.id.videoId">{{item.snippet.title}}</a>
				</h5>
				{{item.snippet.description}}
			</div>	
			

		</li>			  
		
</template>
<script>
	export default{
		name:'videoItemList',
		props:['item'],
		methods:{
			onVideoSelect(){
				this.$emit('videoSelect',this.item);
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
		background-color:#eee;
	}
	
</style>