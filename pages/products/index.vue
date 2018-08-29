<template>
	<section class="container">
		<!-- banner -->
      	<commonBanner :bannerSrc="bannerSrc"></commonBanner>
      	<!-- Products Class start -->
      	<div id="products-class">
      		<!-- Latest Products satrt -->
			<prodKinds :prodList="indexProdList5" :prodKindsData="latestProdData"></prodKinds>
      		<!-- Latest Products end -->
      		<!-- Living Room satrt -->
			<prodKinds :prodList="indexProdList1" :prodKindsData="livingRoomData"></prodKinds>
      		<!-- Living Room end -->
      		<!-- Dining Room satrt -->
			<prodKinds :prodList="indexProdList2" :prodKindsData="diningRoomData"></prodKinds>
      		<!-- Dining Room end -->
      		<!-- Bedroom furniture satrt -->
			<prodKinds :prodList="indexProdList3" :prodKindsData="bedRoomData"></prodKinds>
      		<!-- Bedroom furniture end -->
      		<!-- Study furniture satrt -->
			<prodKinds :prodList="indexProdList4" :prodKindsData="studyRoomData"></prodKinds>
      		<!-- Study furniture end -->
      	</div>
      	<!-- Products Class end -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import prodKinds from '~/components/products/prodKinds'
  	import prodListShow from '~/components/common/prodListShow'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/prodBanner1.jpg',
				latestProdData: {
					prodKindsTitleC: '最新产品',
					prodKindsTitleE: 'Latest Products',
					typeId: 97,
					showMore: false,
					showNewMore: true,
					showBgColor: false
				},
				livingRoomData: {
					prodKindsTitleC: '客厅家具',
					prodKindsTitleE: 'Living Room',
					typeId: 1,
					showMore: true,
					showBgColor: true
				},
				diningRoomData: {
					prodKindsTitleC: '餐厅家具',
					prodKindsTitleE: 'dining Room',
					typeId: 2,
					showMore: true,
					showBgColor: false
				},
				bedRoomData: {
					prodKindsTitleC: '卧室家具',
					prodKindsTitleE: 'Bedroom furniture',
					typeId: 3,
					showMore: true,
					showBgColor: true
				},
				studyRoomData: {
					prodKindsTitleC: '书房家具',
					prodKindsTitleE: 'Study furniture',
					typeId: 4,
					showMore: true,
					showBgColor: false
				}
			}
		},
		head (){
			return {
				title: this.metaData.navigationTitle,
				meta: [
					{name: 'keywords',hid: 'keywords',content:`${this.metaData.navigationKeyword}`},
					{name:'description',hid:'description',content:`${this.metaData.navigationDescription}`}
				]
			}
		},
		async asyncData ({params,store}){
			//head信息
			let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/4`);

			let indexProdList1 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/1`);
			let indexProdList2 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/2`);
			let indexProdList3 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/3`);
			let indexProdList4 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/4`);
			let indexProdList5 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/97`);

			return {
				metaData: metaData.data,
				indexProdList1: indexProdList1.data,
				indexProdList2: indexProdList2.data,
				indexProdList3: indexProdList3.data,
				indexProdList4: indexProdList4.data,
				indexProdList5: indexProdList5.data
			}
		},
		components: {
			commonBanner,
			prodKinds,
			prodListShow
		}
	}
</script>
