<template>
	<div v-if="video" class="mt-4">

		 <iframe width="350" height="315" :src="'https://www.youtube.com/embed/'+video.id.videoId+'?autoplay=1'" 
			allowfullscreen border="0">
		</iframe> 
		<p class="text-justify">{{video.snippet.title}} </p>
		<p>by {{video.snippet.channelTitle}}</p>
	</div>
</template>

<script>
	export default{
		name: 'VideoDetail',
		props:['video']
	}
</script>

<style scoped>
	div{
		position: fixed;
	}
</style>