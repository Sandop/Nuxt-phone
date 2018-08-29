<template>
	<section class="container">
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		
		<!-- 推荐资讯部分 -->
		<newsRecomInfo :recomInfo="recomInfo"></newsRecomInfo>
		<!-- 推荐资讯部分结束 -->
		<!-- 公司和行业资讯部分 -->
		<newsComIndusInfo :companyInfo="companyInfo" :industryInfo="industryInfo"></newsComIndusInfo>
		<!-- 公司和行业资讯结束 -->
		
		<!-- 家具百科部分 -->
		<newsFurnitureInfo :furnitureInfo="furnitureInfo"></newsFurnitureInfo>
		<!-- 家具百科部分结束 -->

		<!-- 品牌选购部分 -->
		<newsBrandInfo :brandInfo="brandInfo"></newsBrandInfo>
		<!-- 品牌选购部分结束 -->

		<!-- 装修摆放部分 -->
		<newsDecoratInfo :decorationInfo="decorationInfo"></newsDecoratInfo>
		<!-- 装修摆放部分结束 -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import newsRecomInfo from '~/components/news/newsRecomInfo'
	import newsComIndusInfo from '~/components/news/newsComIndusInfo'
	import newsFurnitureInfo from '~/components/news/newsFurnitureInfo'
	import newsBrandInfo from '~/components/news/newsBrandInfo'
	import newsDecoratInfo from '~/components/news/newsDecoratInfo'

	export default {
		data (){
			return{
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/news/news_banner.jpg',
			}
		},
		components: {
			commonBanner,
			newsRecomInfo,
			newsComIndusInfo,
			newsFurnitureInfo,
			newsBrandInfo,
			newsDecoratInfo
		},
		head () {
		  return {
		    title:this.metaData.navigationTitle,
		    meta: [
		      {name:'keywords',hid: 'keywords',content:`${this.metaData.navigationKeyword}`},
		      {name:'description',hid:'description',content:`${this.metaData.navigationDescription}`}
		    ]
		  }
		},
		async asyncData({params,store}){
			//head信息
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/12`);
			//推荐资讯
			let recomData = await axios(`${store.state.wordpressAPI}/article/getArticleCenterRecommends`);
	        //公司资讯
	        let companyData = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/1/5`);

	        //行业资讯
	        let industryData = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/5/5`);
	        //家具百科
	        let furnitureData = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/2/4`);

	        //品牌选购
	        let brandData = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/3/4`);

	        //装修摆放
	        let decorationData = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/4/12`);
	        return {
	        	metaData: metaData.data,
	        	recomInfo: recomData.data,
	        	companyInfo: companyData.data,
	        	industryInfo: industryData.data,
	        	furnitureInfo: furnitureData.data,
	        	brandInfo: brandData.data,
	        	decorationInfo: decorationData.data
	        }

	    }
	}
	
</script>