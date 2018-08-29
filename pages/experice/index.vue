<template>
	<section class="container">
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<expericeIdea></expericeIdea>
		<expericeNewModel></expericeNewModel>
		<experienceServer></experienceServer>
		<expericeDesign></expericeDesign>
	</section>
</template>


<script>
	import axios from 'axios'
	import expericeDesign from '~/components/experice/expericeDesign'
	import commonBanner from '~/components/common/commonBanner'
	import expericeIdea from '~/components/experice/expericeIdea'
	import expericeNewModel from '~/components/experice/expericeNewModel'
	import experienceServer from '~/components/experice/experienceServer'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/experice/banner.png'
			}
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
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/3`);
		  return {
		    metaData: metaData.data,
		  } 
		},
		components: {
			commonBanner,
			expericeIdea,
			expericeNewModel,
			experienceServer,
			expericeDesign
		}
	}
</script>
