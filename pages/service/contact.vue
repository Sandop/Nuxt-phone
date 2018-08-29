<template>
	<section class="container">
		<!-- 轮播图部分开始 -->
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- 轮播图部分结束 -->
		
		<!-- Place Map start -->
		<div class="contact_map_wrap">
			<expericeMap :mapData="mapData"></expericeMap>
		</div>
		<!-- Place Map end -->
			
		<!-- Contact Us start -->
		<contactUs></contactUs>
		<!-- Contact Us end -->

		<!-- Customer service start -->
		<contactService></contactService>
		<!-- Customer service end -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import expericeMap from '~/components/experice/expericeMap'
	import contactUs from '~/components/contact/contactUs'
	import contactService from '~/components/contact/contactService'


	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/banner.jpg',
				mapData: {
					longitude: 113.845282,
					latitude: 22.613041,
					title: '深圳市田田家园家具有限公司',
					description: '地址：深圳市宝安区西乡街道泰华梧桐岛11栋5'
				},
			}
		},
		components: {
			commonBanner,
			expericeMap,
			contactUs,
			contactService
		},
		head () {
		  return {
		    title:this.metaData.navigationTitle,
		    meta: [
		      {name:'keywords',hid: 'keywords',content:`${this.metaData.navigationKeyword}`},
		      {name:'description',hid:'description',content:`${this.metaData.navigationDescription}`}
		    ],
			script: [
				{src:'http://api.map.baidu.com/api?v=2.0&ak=MDdqxkqhQzfdBzfu2tfGiidGbHgTfGrB'}
			]
		  }
		},
		async asyncData({params,store}){
		  //head信息
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/17`);
		  return {
		    metaData: metaData.data,
		  } 
		}
	}
</script>

<style scoped>
	.contact_map_wrap {
		width: 9.347rem;
		height: 8rem;
		margin: 1rem auto 0;
	}
</style>