<template>
	<section class="container">
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		
		<!-- 新闻主体列表部分 -->
		<div id="news-list">
			<div class="news-list-content">
				<div class="news-list-content-box">
					<div class="news-list-container">
						<ul class="news-list-nav">
							<li class="news-list-kind" :class="{active:list.articleCategoryId == $route.params.category}" v-for="(list,index) in $store.state.headNewsNav" :key="index">
								<nuxt-link :to="{name: 'news-category',params: {category: list.articleCategoryId}}">{{list.articleCategoryName}}</nuxt-link>
							</li>
						</ul>
						<div class="news-list-tab-content">
							<div class="news-list-tab-box">
								<ul>
									<li class="news-list-details" v-for="(list,index) in newsListData" :key="index">
										<div class="news-list-details-box">
											<div class="news-list-left">
												<nuxt-link :to="{name:'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}"><img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt"></nuxt-link>
											</div>
											<div class="news-list-right">
												<div class="news-list-title">
													<nuxt-link :to="{name:'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}"><h2>{{list.articleName}}</h2></nuxt-link>
												</div>
												<div class="news-list-desc">{{getTxt(list.articleText)}}</div>
												<div class="news-list-time">
													<p>{{getTime(list.articleAddTime,0)}}</p>
												</div>
											</div>
										</div>
			                       	</li>
								</ul>
								<div class="news-list-more-box" @click="getMoreNewsList" v-if="newsListData.length < total">
									<p>查看更多 ></p>
								</div>
								<div class="news-list-more-box"  v-if="newsListData.length >= total">
									<p>------我是有底线哒O(∩_∩)O~------</p>
								</div>
							</div>							
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- 新闻主体列表结束 -->

		<!-- Recommended Article Start-->
		<newsRecomArticle :recomArticleData="recomArticleData"></newsRecomArticle>
		<!-- Recommended Article End-->

		<!-- Recommended Products Start-->
		<newsRecomProd :recomProductsData="recomProductsData" :recomProductsTitle="recomProductsTitle"></newsRecomProd>
		<!-- Recommended Products End-->

	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import newsRecomArticle from '~/components/news/newsRecomArticle'
	import newsRecomProd from '~/components/news/newsRecomProd'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/news/news_banner.jpg',
				recomProductsTitle: '推荐产品',
				currentPage: 1
			}
		},
		head (){
			return {
				title: this.metaData.title,
				meta: [
					{name: 'keywords',hid: 'keywords', content: `${this.metaData.keyword}`},
					{name:'description',hid:'description',content:`${this.metaData.description}`}
				]
			}
		},
		validata ({ params }){
			return /^\d+$/.test(params.category)
		},
		async asyncData ({store,params}){
			let newsCategoryId = params.category;
			
			//新闻列表
			let newsListData = await axios(`${store.state.wordpressAPI}/article/getArticles/${newsCategoryId}/1/6`);

			//推荐文章
			let recomArticleData = await axios.get(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/${newsCategoryId}/4`);
			//推荐产品
			let recomProductsData = await axios.get(`${store.state.wordpressAPI}/product/getProRandom/4`);
			return {
				metaData: newsListData.data,
				newsListData: newsListData.data.list,
				total: newsListData.data.total,	
				recomArticleData: recomArticleData.data,
				recomProductsData: recomProductsData.data
			}
		},
		components: {
			commonBanner,
			newsRecomArticle,
			newsRecomProd
		},
		methods: {
            getTxt (str,num = 44){
	    		var txt = str.replace(/<\/?.+?>/g,"").replace(/&nbsp;/gi,"").replace(/(^\s+)|(\s+$)/g,"").replace(/\s/g,''); 
	  			txt = txt.length < 170 ? txt : txt.substring(0,num).concat('...');
	    		return txt;
			},
			getTime(time,num1=5,num2=10){
                var time = time.slice(num1, num2);
                return time;
			},
			getMoreNewsList (){
				this.currentPage ++;
				let categoryId = this.$route.params.category;
		       // ajax请求, 向后台发送 currentPage, 来获取对应的数据
		        axios.get(`${this.$store.state.wordpressAPI}/article/getArticles/${categoryId}/${this.currentPage}/6`)
		                .then((response)=> {
							let newNewsList = response.data.list;
							this.newsListData.push(...newNewsList)
							this.total = response.data.total;
		                })
		                .catch(function (error) {
		                 	console.log(error);
		                });
			}
		}
	}
</script>

<style scoped>
	div#news-list {
		width:  100%;
	}

	.news-list-content {
		width: 100%;
	}

	.news-list-content-box {
		width: 100%;
	}

	.news-list-container {
		width: 100%;
	}

	ul.news-list-nav {
		display:  flex;
		overflow:  hidden;
		width:  100%;
		padding: 1.32rem 0 0.24rem;
		justify-content: center;
		flex-wrap:  wrap;
		text-align:  center;
	}

	li.news-list-kind {
		width: 2.053rem;
		height: 0.8rem;
		margin: 0.12rem;
		border: solid 0.04rem transparent;
	}

	li.news-list-kind.active {
		border: solid 0.04rem #000;
	}

	li.news-list-kind a {
		font-size: 0.32rem;
		line-height: 0.8rem;
		color: #000000;
	}

	.news-list-tab-content {
		width: 100%;
	}

	.news-list-tab-box {
		width: 100%;
	}

	.news-list-tab-box ul {
		width: 100%;
	}

	li.news-list-details {
		width:  100%;
		padding: 0.8rem 0;
		border-bottom: 0.027rem solid rgba(46, 44, 58, 0.2);
	}

	.news-list-details-box {
		overflow:  hidden;
		width: 100%;
		padding:  0 0.373rem 0 0.33rem;
		box-sizing:  border-box;
	}

	.news-list-left {
		float:  left;
		overflow:  hidden;
		width: 3.733rem;
		height: 2.667rem;
	}

	.news-list-left a {
		display:  block;
		width:  100%;
		height: 100%;
	}

	.news-list-left img {
		width: 100%;
		height: 100%;
	}

	.news-list-right {
		float:  right;
		overflow:  hidden;
		width: 5.12rem;
	}

	.news-list-title {
		width: 100%;
		height: 0.8rem;
		font-size: 0.373rem;
		font-weight: bold;
		line-height: 0.8rem;
	}

	.news-list-title a {
		display:  block;
		overflow:  hidden;
		width: 100%;
		height:  100%;
		color: #22202b;
		text-overflow:  ellipsis;
		white-space:  nowrap;
	}

	.news-list-title a h2{
		display:  block;
		overflow:  hidden;
		width: 100%;
		height:  100%;
		font-weight: bold;
		text-overflow:  ellipsis;
		white-space:  nowrap;
	}

	.news-list-desc {
		width:  100%;
		font-size: 0.32rem;
		line-height: 0.44rem;
		color: #858585;
	}

	.news-list-time {
		width: 100%;
		font-size: 0.213rem;
		text-align: right;
		line-height: 0.6rem;
		color: #999999;
	}

	.news-list-more-box {
		width:  100%;
		height:  1.173rem;
		border-bottom: 0.027rem solid rgba(46, 44, 58, 0.2);
		font-size: 0.373rem;
		text-align:  center;
		line-height: 1.173rem;
		color: #4b4b4b;
	}
</style>