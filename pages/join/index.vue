<template>
	<section class="container">
		<!-- 轮播图部分开始 -->
		<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- 轮播图部分结束 -->

		<!-- The future start -->
		<joinFuture></joinFuture>
		<!-- The future end -->
		
		<!-- who are we start -->
		<joinVisneyIntro></joinVisneyIntro>
		<!-- who are we end -->

		<!-- Who are the partners start -->
		<joinPartners></joinPartners>
		<!-- Who are the partners end -->
		
		<!-- What is our purpose start -->
		<joinPurpose></joinPurpose>
		<!-- What is our purpose end -->

		<!-- join protection start -->
		<joinProtection></joinProtection>
		<!-- join protection end -->

		<!-- join advantages start -->
		<joinAdvantages></joinAdvantages>
		<!-- join advantages end -->

		<!-- join case start -->
		<joinCase></joinCase>
		<!-- join case end -->

		<!-- join support start -->
		<joinSupport></joinSupport>
		<!-- join support end -->

		<!-- join city start -->
		<joinCity></joinCity>
		<!-- join city end -->

		<!-- join requires start -->
		<joinRequires></joinRequires>
		<!-- join requires end -->
		
		<!-- join partner contact start -->
		<joinPartnerContact></joinPartnerContact>
		<!-- join partner contact end -->
		
		<!-- join footer start -->
		<joinFooter></joinFooter>
		<!-- join footer start -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import joinFuture from '~/components/join/joinFuture'
	import joinVisneyIntro from '~/components/join/joinVisneyIntro'
	import joinPartners from '~/components/join/joinPartners'
	import joinPurpose from '~/components/join/joinPurpose'
	import joinProtection from '~/components/join/joinProtection'
	import joinAdvantages from '~/components/join/joinAdvantages'
	import joinCase from '~/components/join/joinCase'
	import joinSupport from '~/components/join/joinSupport'
	import joinCity from '~/components/join/joinCity'
	import joinRequires from '~/components/join/joinRequires'
	import joinPartnerContact from '~/components/join/joinPartnerContact'
	import joinFooter from '~/components/join/joinFooter'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/business_banner.jpg'
			}
		},
		components: {
			commonBanner,
			joinFuture,
			joinVisneyIntro,
			joinPartners,
			joinPurpose,
			joinProtection,
			joinAdvantages,
			joinCase,
			joinSupport,
			joinCity,
			joinRequires,
			joinPartnerContact,
			joinFooter
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
		    let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/14`);
		  return {
		    metaData: metaData.data,
		  } 
		}
	}
</script>

