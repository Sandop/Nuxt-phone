<template>
	<section class="cotainer">
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- News View details start-->
		<newsView :articleData="articleData" :preNextData="preNextData"></newsView>
		<!-- News Views details end-->

		<!-- Related Article Start-->
		<newsRelatedArticle :relatedArticleData="relatedArticleData"></newsRelatedArticle>
		<!-- Related Article End-->

		<!-- Latest Articles start-->
		<newsLatestArticle :latestArticleData="latestArticleData"></newsLatestArticle>
		<!-- Latest Articles end-->

		<!-- Love Products Start-->
		<newsLove :loveArticleData="loveArticleData"></newsLove>
		<!-- Love Products End-->
	</section>
</template>

<script>
	import axios from 'axios'
	import newsView from '~/components/news/newsView'
	import commonBanner from '~/components/common/commonBanner'
	import newsRelatedArticle from '~/components/news/newsRelatedArticle'
	import newsLatestArticle from '~/components/news/newsLatestArticle'
	import newsLove from '~/components/news/newsLove'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/news/news_banner.jpg'
			}
		},
		validate({ params }) {
	        return /^\d+$/.test(params.id)
	    },
		async asyncData ({params,query,store}){
			let id = params.id;
			let parId = query.category;
	    	//详情数据
	    	let articleData = await axios.get(`${store.state.wordpressAPI}/article/getArticleDetails/${id}`);
	    	//上下篇数据
	    	let preNextData = await axios.get(`${store.state.wordpressAPI}/article/getArticleNextAndBefore/${parId}/${id}`);
	    	//相关文章
	    	let relatedArticleData = await axios.get(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/${parId}/4`);
	    	//最新文章
	    	let latestArticleData = await axios.get(`${store.state.wordpressAPI}/article/getArticleNew/2`);
	    	//猜你喜欢
	    	let loveArticleData = await axios.get(`${store.state.wordpressAPI}/article/getArticleRandom`);

	    	return {
	    		articleData: articleData.data,
	    		preNextData: preNextData.data.list,
	    		relatedArticleData: relatedArticleData.data,
	    		latestArticleData: latestArticleData.data,
	    		loveArticleData: loveArticleData.data
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
			newsView,
			newsRelatedArticle,
			newsLatestArticle,
			newsLove
		}
	}
</script>
