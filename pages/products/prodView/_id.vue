<template>
	<section class="cotainer">
 		
		<!-- Products show start -->
		<div id="products-show">
			<!-- Products top show start -->
			<prodViewInfo :prodViewData="prodViewData"></prodViewInfo>
			
			<!-- Products top show end -->

			<!-- Products details box start -->
			<prodDetails :prodViewData="prodViewData"></prodDetails>
			<!-- Products details box end -->
		</div>
		<!-- Products show end -->

		<!-- Related Products start -->
		<div id="related_products_wrap products_others_wrap">
			<div class="related_products_box products_others_box">
				<div class="related_products_title products_others_title">
					<p>相关产品</p>
				</div>
				<div class="related_prod_list_box products_others_list_box">
					<prodListShow :prodList="relatedProdData" :showBgColor="false"></prodListShow>
				</div>
			</div>
		</div>
		<!-- Related Products end -->

		<!-- You Like start -->
		<div id="products_like_wrap products_others_wrap">
			<div class="products_like_box products_others_box">
				<div class="prod_like_title products_others_title">
					<p>猜你喜欢</p>
				</div>
				<div class="prod_like_list_box products_others_list_box">
					<prodListShow :prodList="likeProdData" :showBgColor="false"></prodListShow>
				</div>
			</div>
		</div>
		<!-- You Like end -->
	</section>
</template>

<script>
	import axios from 'axios'
  	import prodListShow from '~/components/common/prodListShow'
	import prodViewInfo from '~/components/products/prodViewInfo'
	import prodDetails from '~/components/products/prodDetails'

	export default {
		head (){
			return {
				title: this.prodViewData.proMetaTitle,
				meta: [
					{name: 'keywords',hid: 'keywords',content: `${this.prodViewData.proMetaKeyWord}`},
					{name: 'description',hid: 'description',content: `${this.prodViewData.proMetaDescription}`}
				]
			}
		},
		validata ({ params }){
			return /^\d+$/.test(params.id)
		},
		async asyncData ({params,query,store}){
			let typeId = query.typeId;
			let classId = query.classId;
			let id = params.id;
			//详情信息
			let prodViewData = await axios(`${store.state.wordpressAPI}/product/detail/${id}`);
			//相关产品
			let relatedProdData = await axios(`${store.state.wordpressAPI}/product/getProByTpyeId/${classId}/2`);
			//猜你喜欢
			let likeProdData = await axios(`${store.state.wordpressAPI}/product/getProRandom/2`);
			return {
				prodViewData: prodViewData.data,
				relatedProdData: relatedProdData.data,
				likeProdData: likeProdData.data,
				bigImage: prodViewData.data.proImgs,
				middleImage: prodViewData.data.proImgs,
				smallImage: prodViewData.data.proImgs
			}
		},
		components: {
			prodListShow,
			prodViewInfo,
			prodDetails
		}
	}
</script>

<style scoped>

	div#products-show {
		overflow: hidden;
		width: 100%;
		height: auto;
	}

	.products_others_wrap {
		width: 100%;
	}

	.products_others_box {
		width: 100%;
	}

	.products_others_title {
		width:  100%;
		font-size: 0.48rem;
		text-align: center;
		line-height: 1rem;
		color: #22202b;
	}

	.products_others_title p {
		position: relative;
		display: inline-block;
	}

	.products_others_title p:after {
		content: '';
		position: absolute;
		bottom: 0;
		left: 50%;
		width: 0.827rem;
		height: 0.027rem;
		transform: translateX(-50%);
		background-color: #d4c2a1;
	}

	.products_others_list_box {
		width: 100%;
		padding: 0.787rem 0 0.96rem;
	}

</style>