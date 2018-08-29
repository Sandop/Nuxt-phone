<template>
	<div>
	  	<div class="products-tab-box">
			<ul>
				<li class="products-kind-list" v-for="(item,index) in prodList" :key="index" v-if="index < showNum" :class="{background_color: showBgColor}">
					<div class="products-kind-list-img">
					<nuxt-link :to="{name: 'products-prodView-id',params:{id: item.proId},query: {typeId: item.proPositionId,classId: item.proTypeId}}">
						<img :src="item.proImgs[0].proImgSrc" :alt="item.proImgs[0].proImgAlt">
					</nuxt-link>
					</div>
					<div class="products-kind-name">
					<nuxt-link :to="{name: 'products-prodView-id',params:{id: item.proId},query: {typeId: item.proPositionId,classId: item.proTypeId}}">{{item.proName}}</nuxt-link>
					</div>
					<div class="products-kind-price">
						￥<span class="price-num">{{item.proPrice}}</span>
					</div>
				</li>   
			</ul>
	  	</div>
		<div class="products-more" v-if="showMore">
			<nuxt-link :to="{name: 'products-typeId',params: {typeId: typeId}}">了解更多 ></nuxt-link>
		</div>
		<div class="products-more" v-if="showNewMore">
			<nuxt-link to="products/newPro">了解更多 ></nuxt-link>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'prodListShow',
		props: {
			prodList: {
				type: Array
			},
			showMore: {
				type: Boolean,
				default: false
			},
			showNewMore: {
				type: Boolean,
				default: false
			},
			typeId: {
				type: Number,
				default: 1
			},
			showBgColor: {
				type: Boolean,
				default: true
			},
			showNum: {
				type: Number,
				default: 6
			}
		}
	}
	
</script>

<style scoped>
	.products-tab-box {
		width:  100%;
	}

	ul {
		display:  flex;
		justify-content:  center;
		align-items:  center;
		flex-wrap:  wrap;
	}

	li.products-kind-list {
		width: 4.533rem;
		margin: 0.106rem 0.1135rem;
	}

	.background_color {
		background-color: #f5f5f5;
	}

	.products-kind-list-img {
		width:  100%;
		height: 3.413rem;
		padding: 0.2065rem 0;
		box-sizing:  border-box;
	}

	.products-kind-list-img a {
		position:  relative;
		display:  block;
		overflow:  hidden;
		width:  100%;
		height:  100%;
	}

	.products-kind-list-img a img {
		position: absolute;
		top: 50%;
		left: 50%;
		overflow: hidden;
		transform: translate(-50%,-50%) scale(0.18);
	}

	.products-kind-name {
		overflow:  hidden;
		width:  100%;
		height: 0.407rem;
		margin: 0.1rem 0;
		padding: 0 5%;
		box-sizing:  border-box;
		font-size: 0.32rem;
		line-height: 0.407rem;
		text-align: center;
	}

	.products-kind-name a {
		display:  block;
		overflow:  hidden;
		width:  100%;
		height: 100%;
		color: #979797;
		white-space:  nowrap;
		text-overflow:  ellipsis;
	}

	.products-kind-price {
		width:  100%;
		padding: 0.28rem 0 0.427rem;
		text-align:  center;
		font-size: 0.18rem;
		line-height: 0.18rem;
	}

	span.price-num {
		font-family: SourceHanSerifCN-Bold;
		font-size: 0.234rem;
		font-weight: bold;
		line-height: 0.34rem;
		color: #22202b;
	}

	.products-more {
		width:  100%;
		height: 0.4rem;
		padding-top: 0.787rem;
		text-align:  center;
	}

	.products-more a {
		display:  block;
		width:  100%;
		height:  100%;
		font-family: MicrosoftYaHei-Bold;
		font-size: 0.32rem;
		font-weight: bold;
		line-height: 0.187rem;
		color: #000000;
	}
</style>
