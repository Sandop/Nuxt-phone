<template>
	<section class="container">
		<!-- banner start -->
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- banner end -->
		
		<!-- Questions List start -->
		<div id="questions_wrap">
			<div class="questions_box">
				<div class="questions_list_box">
					<ul>
						<li class="questions_list" v-for="list in listData" :key="list.articleId">
							<div class="questions_list_cont">
								<div class="questions_list_left">
									<nuxt-link :to="{name:'service-id',params:{category: list.articleCategoryId,id:list.articleId}}"><img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt"></nuxt-link>
								</div>
								<div class="questions_list_right">
									<div class="questions_list_title">
										<nuxt-link :to="{name:'service-id',params:{id:list.articleId,category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
									</div>
									<div class="questions_list_desc">{{getTxt(list.articleText)}}</div>
									<div class="questions_list_time">
										<p>{{getTime(list.articleAddTime,0)}}</p>
									</div>
								</div>
							</div>
                      	</li>
					</ul>
				</div>
				<div class="questions_list_pagination_box" @click="getMoreList" v-if="listData.length < total">
					<p>查看更多 ></p>
				</div>
				<div class="questions_list_pagination_box"  v-if="listData.length >= total">
					<p>------我是有底线哒O(∩_∩)O~------</p>
				</div>
			</div>
		</div>
		<!-- Questions List start -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/questions_banner.jpg',
		        currentPage: 1   // 当前的页数
			}
		},
		components: {
			commonBanner
		},
		methods : {
            getMoreList (){
				this.currentPage ++;
		       // ajax请求, 向后台发送 currentPage, 来获取对应的数据
		        axios.get(`${this.$store.state.wordpressAPI}/article/getArticles/20/${this.currentPage}/6`)
		                .then((response)=> {
							let newList = response.data.list;
							this.listData.push(...newList)
							this.total = response.data.total;
		                })
		                .catch(function (error) {
		                 	console.log(error);
		                });
			},
            getTxt (str){
	    		var txt = str.replace(/<\/?.+?>/g,"").replace(/(^\s+)|(\s+$)/g,"").replace(/\s/g,''); 
	  			txt = txt.length < 170 ? txt : txt.substring(0,44).concat('...');
	    		return txt;
			},
			getTime(time,num1=5,num2=10){
                var time = time.slice(num1, num2);
                return time;
			}
        },
        head (){
        	return {
        		title:this.metaData.navigationTitle,
        		meta: [
        			{name: 'keywords',hid: 'keywords',content: `${this.metaData.navigationKeyword}`},
        			{name: 'description',hid: 'description',content: `${this.metaData.navigationDescription}`}
        		]
        	}
        },
        async asyncData ({store,params}){
        	//meta&title
        	let metaData = await axios.get(`${store.state.wordpressAPI}/NavigationMeta/get/18`);
        	//question list
			let listData = await axios.get(`${store.state.wordpressAPI}/article/getArticles/20/1/6`);
        	return {
				metaData: metaData.data,
				listData: listData.data.list,
				total: listData.data.total 	//请求数据的总条数
        	}
        }
	}
</script>

<style>
	div#questions_wrap {
		width: 100%;
	}

	.questions_list_box {
		width: 100%;
	}

	.questions_list_box ul {
		width: 100%;
	}

	li.questions_list {
		width: 100%;
		padding: 0.8rem 0;
		border-bottom: 0.027rem solid rgba(46, 44, 58, .2);
	}

	.questions_list_cont {
		overflow: hidden;
		width: 100%;
		padding: 0 0.373rem 0 0.33rem;
		box-sizing: border-box;
	}

	.questions_list_left {
		float: left;
		overflow: hidden;
		width: 3.733rem;
		height: 2.667rem;
	}

	.questions_list_left a {
		display: block;
		width: 100%;
		height: 100%;
	}

	.questions_list_left img {
		width:  100%;
		height: 100%;
	}

	.questions_list_right {
		float: right;
		overflow: hidden;
		width: 5.12rem;
	}

	.questions_list_title {
		width: 100%;
		height: 0.8rem;
		font-size: 0.373rem;
		font-weight: bold;
		line-height: 0.8rem;
	}

	.questions_list_title a {
		display: block;
		overflow: hidden;
		width: 100%;
		height: 100%;
		color: #22202b;
		text-overflow: ellipsis;
		white-space: nowrap;
	}

	.questions_list_desc {
		width: 100%;
		font-size: 0.32rem;
		line-height: 0.44rem;
		color: #858585;
	}

	.questions_list_time {
		width: 100%;
		font-size: 0.213rem;
		text-align: right;
		line-height: 0.6rem;
		color: #999999;
	}

	.questions_list_pagination_box {
		width:  100%;
		height:  18.768px;
		height:  1.173rem;
		border-bottom: 0.432px solid rgba(46, 44, 58, .2);
		border-bottom: 0.027rem solid rgba(46, 44, 58, .2);
		font-size: 5.968px;
		font-size: 0.373rem;
		text-align:  center;
		line-height: 18.768px;
		line-height: 1.173rem;
		color: #4b4b4b;
	}
</style>

