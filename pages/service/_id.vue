<template>
	<section class="cotainer">
		<!-- banner start -->
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- banner end -->

		<!-- Questions View details start-->
		<div class="question_details">
			<newsView :articleData="articleData" :preNextData="preNextData" :isQuestions="true"></newsView>
		</div>
		<!-- Questions Views details end-->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import newsView from '~/components/news/newsView'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/questions_banner.jpg'
			}
		},
		validate({ params }) {
	        return /^\d+$/.test(params.id)
	    },
		async asyncData ({params,store}){
			let parId = params.category;
	    	//详情数据
	    	let articleData = await axios.get(`${store.state.wordpressAPI}/article/getArticleDetails/${params.id}`);

	    	//上下篇数据
	    	let preNextData = await axios.get(`${store.state.wordpressAPI}/article/getArticleNextAndBefore/20/${params.id}`);
	    	return {
	    		articleData: articleData.data,
	    		preNextData: preNextData.data.list
	    	}
		},
		head (){
			return {
				title: this.articleData.articleMetaTitle,
				meta: [
					{name: 'keywords',hid: 'keywords',content: `${this.articleData.articleKeyWord}`},
					{name: 'description',hid: 'description',content: `${this.articleData.articleMetaDescription}`}
				]
			}
		},
		components: {
			commonBanner,
			newsView
		}
	}
</script>
<style>
	.question_details {
		padding-bottom: 0.6rem;
	}
</style>



