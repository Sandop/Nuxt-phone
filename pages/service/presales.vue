<template>
	<section class="container">
		<!-- banner start -->
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- banner end -->
		
		<!-- Pre sale service commitment start -->
		<preSales></preSales>
		<!-- Pre sale service commitment  end -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import preSales from '~/components/sales/preSales'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/after_sales_banner.jpg',

			}
		},
		components: {
			commonBanner,
			preSales
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
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/15`);
		  return {
		    metaData: metaData.data,
		  } 
		}
	}
</script>