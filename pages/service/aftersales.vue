<template>
	<section class="container">
		<!-- banner start -->
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- banner end -->
		
		<!-- After sale service commitment start -->
		<afterSales></afterSales>
		<!-- After sale service commitment  end -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import afterSales from '~/components/sales/afterSales'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/after_sales_banner.jpg',

			}
		},
		components: {
			commonBanner,
			afterSales
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
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/16`);
			return {
				metaData: metaData.data,
			} 
		}
	}
</script>
