<template>
	<div id="dream_together_wrap">
		<div class="dream_together_box">
			<div class="dream_together_title_box">
				<div class="dream_together_titleC">
					<h2>2018梦想同行</h2>
				</div>
				<div class="dream_together_titleE">
					<p>Dream Together</p>
				</div>
				<div class="dream_together_title_desc">
					<p>我们所有的努力，旨在打造一个宾至如归的理想状态。</p>
					<p>我们推崇简单、自然、环保健康的生活方式，这即是Olivelife---生态生活的意义</p>
				</div>
			</div>
			<div class="dream_together_video">
				<video id="story-video" controls="controls" preload="auto">
					<source src="~/assets/images/video/dream_together_video.mp4">
				</video>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: 'expericeVideo'
	}
</script>
<style scoped>
	div#dream_together_wrap {
		width:  100%;
		background-color: #f9f9fa;
	}

	.dream_together_box {
		width:  100%;
		text-align:  center;
		padding-bottom: 1.333rem;
	}

	.dream_together_title_box {
		width:  100%;
		padding: 1.293rem 0 0.907rem;
	}

	.dream_together_titleC {
		font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
		font-size: 0.64rem;
		font-weight: 900;
		line-height: 0.7rem;
		color: #22202b;
	}

	.dream_together_titleE {
		font-size: 0.24rem;
		line-height: 0.5rem;
		color: #858585;
	}

	.dream_together_title_desc {
		margin-top: 0.333rem;
		padding: 0 0.88rem 0 0.66rem;
		box-sizing:  border-box;
		font-size: 0.24rem;
		line-height: 0.42rem;
		color: #858585;
	}

	.dream_together_video {
		overflow:  hidden;
		width: 9.173rem;
		height: 6rem;
		margin:  0 auto;
	}

	.dream_together_video video {
		width: 100%;
		height: 100%;
	}
</style>
