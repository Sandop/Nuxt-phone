<template>
	<section class="container">
		<!-- banner -->
		<brandBanner></brandBanner>
		<!-- banner -->
		<!-- brand story -->
		<brandStory></brandStory>
		<!-- brand background -->
		<brandBg></brandBg>

		<!-- 发展历程部分 -->
		<brandDevelopment></brandDevelopment>
		<!-- 发展历程部分结束 -->
		
		<!-- 品牌理念部分 -->
		<brandConcept></brandConcept>
		<!-- 品牌理念部分结束 -->
		
		<!-- 品牌实力部分 -->
		<brandStrength></brandStrength>
		<!-- 品牌实力部分结束 -->

	</section>
</template>


<script>
	import axios from 'axios'
	import brandBanner from '~/components/brand/brandBanner'
	import brandStory from '~/components/brand/brandStory'
	import brandBg from '~/components/brand/brandBg'
	import brandDevelopment from '~/components/brand/brandDevelopment'
	import brandConcept from '~/components/brand/brandConcept'
	import brandStrength from '~/components/brand/brandStrength'

	export default {
		data (){
			return {
			}
		},
		components: {
			brandBanner,
			brandStory,
			brandBg,
			brandDevelopment,
			brandConcept,
			brandStrength
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
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/2`);
		  return {
		    metaData: metaData.data,
		  } 
		}
	}
</script>
