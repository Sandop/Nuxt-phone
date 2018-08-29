<template>
	<section class="container">
		<!-- banner -->
      	<commonBanner :bannerSrc="bannerSrc"></commonBanner>
		<!-- Products list start -->

		<!-- Products select start -->
		<div id="products-content">
			<!-- products-select start -->
			<div id="products-select">
				<div class="products-select-box">
					<div class="furniture-place">
						<div class="furniture-place-kinds">
							<ul>
								<li class="furniture-place-kinds-list" v-for="(item,index) in $store.state.headProdNav" :key="index" :class="{active: item.proCategoryId == $route.params.typeId}"  @click="showClassData" v-if="item.proCategoryId == $route.params.typeId">
									{{item.proCategoryName}}
								</li>
								<li class="furniture-place-kinds-list" @click="showMaterialsData">
									家具材质
								</li>
								<li class="furniture-place-kinds-list" @click="showSeriesData">
									家具系列
								</li>
								<li class="furniture-place-kinds-list" @click="showStyleData">
									家具风格
								</li>
							</ul>
						</div>
					</div>
					<div class="furniture-class" v-show="showClass">
						<div class="furniture-class-kinds">
							<ul>
								<li class="furniture-class-kinds-list" @click="getClassIdProdList(null)" :class="{active: null == classId }">
									全部
								</li>
								<li class="furniture-class-kinds-list" v-for="(item,index) in $store.state.headProdNav[$route.params.typeId - 1].children" :key="index" @click="getClassIdProdList(item.proCategoryId)" :class="{active: item.proCategoryId == classId }">
									{{item.proCategoryName}}
								</li> 
							</ul>
						</div>
						<div class="furniture-close-box" @click="closeBtn">
							<div class="furniture-close">X</div>
						</div>
					</div>
					<div class="furniture-materials furniture-class" v-show="showMaterials">
						<div class="furniture-materials-kinds furniture-class-kinds">
							<ul>
								<li class="furniture-materials-kinds-list furniture-class-kinds-list" @click="getTextureIdProdList(null)" :class="{active: null == textureId}">全部</li>
								<li class="furniture-materials-kinds-list furniture-class-kinds-list" v-for="(item,index) in materialsData.children" :key="index" @click="getTextureIdProdList(item.proCategoryId)"  :class="{active: item.proCategoryId == textureId}">
									{{item.proCategoryName}}
								</li>
							</ul>
						</div>
						<div class="furniture-close-box" @click="closeBtn">
							<div class="furniture-close">X</div>
						</div>
					</div>
					<div class="furniture-series furniture-class" v-show="showSeries">
						<div class="furniture-series-kinds furniture-class-kinds">
							<ul>
								<li class="furniture-series-kinds-list furniture-class-kinds-list" @click="getSeriesIdProdList(null)" :class="{active: null == seriesId}">全部</li>
								<li class="furniture-series-kinds-list furniture-class-kinds-list" v-for="(item,index) in seriesData.children" :key="index" @click="getSeriesIdProdList(item.proCategoryId)" :class="{active: item.proCategoryId == seriesId}">{{item.proCategoryName}}</li>
							</ul>
						</div>
						<div class="furniture-close-box" @click="closeBtn">
							<div class="furniture-close">X</div>
						</div>
					</div>
					<div class="furniture-style furniture-class" v-show="showStyle">
						<div class="furniture-style-kinds furniture-class-kinds">
							<ul>
								<li class="furniture-style-kinds-list furniture-class-kinds-list" @click="getStyleIdProdList(null)" :class="{active: null == styleId}">全部</li>
								<li class="furniture-style-kinds-list furniture-class-kinds-list" v-for="(item,index) in styleData.children" :key="index" @click="getStyleIdProdList(item.proCategoryId)" :class="{active: item.proCategoryId == styleId}">{{item.proCategoryName}}</li>
							</ul>
						</div>
						<div class="furniture-close-box" @click="closeBtn">
							<div class="furniture-close">X</div>
						</div>
					</div>
					<div class="products-sequence">
						<div class="compl-sequence"><span>综合排序</span></div>
						<div class="sales-volume" v-if="false">
							<ul>
								<li data-id="0" class="sales-volume-list" @click="getOrderByPageViewsCountProdList" :class="{active: orderByPageViewsCount}">销量</li>
							</ul>
						</div>
						<div class="news-products">
							<ul>
								<li data-id="0" class="news-products-list" @click="getOrderByTimeProdList" :class="{active: orderByTime}">新品</li>
							</ul>
						</div>
						<div class="products-prices">
							<ul>
								<li data-id="0" class="products-prices-list" @click="getOrderByPriceProdList" :class="{active: orderByPrice}">价格</li>
							</ul>
						</div>
					</div>
				</div>
			</div>
			<!-- products-select end -->

			<!-- products-show start -->
			<div id="products-show">
				<div class="products-show-box">
					<div v-if="prodListData.total == 0">
						<p>还没有类似产品哦^_^，请选择其他相关产品，O(∩_∩)O谢谢！</p>
					</div>
					<div v-if="prodListData.total != 0">
      					<prodListShow :prodList="prodListData" :showNum="999999999"></prodListShow>
					</div>
				</div>
			</div>
			<!-- products-show end -->
			
			<!-- products-pagination start-->
			<div id="products-pagination" v-if="prodListData.total != 0">
				<div id="products-more-box" @click="getMoreProdList" v-if="prodListData.length < total">
                    <div class="products-more">
						查看更多 >
					</div>
                </div>
				<div class="products-more-box"  v-if="prodListData.length >= total">
					<div class="products-more">
					------我是有底线哒O(∩_∩)O~------
					</div>
				</div>
			</div>
			<!-- products-pagination end-->
		</div>
		<!-- Products select end -->

		<!-- Products list end -->	
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
  	import prodListShow from '~/components/common/prodListShow'
	import qs from 'qs'

  	export default {
  		data (){
  			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/prodBanner1.jpg',
				//产品筛选
				positionId: this.$route.params.typeId,	//空间Id
				typeId: null,		//类型
				textureId: null,		//材质
				seriesId: null,			//系列
				styleId: null,			//分格
				orderByTime: 0,			//是否根据时间排序，1代表是，0代表否
				orderByPageViewsCount: 0,		//是否销量排序，1代表是，0代表否
				orderByPrice: 0,			//是否根据价格排序，1代表是，0代表否
				//产品分页
				currentPage: 1,   // 当前的页数

				showClass: false,
				showMaterials: false,
				showSeries: false,
				showStyle: false

  			}
  		},
  		head (){
  			return {
	  			title: this.prodListData.title,
				meta: [
					{name: 'keywords',hid: 'keywords',content:`${this.prodListData.keyword}`},
					{name:'description',hid:'description',content:`${this.prodListData.description}`}
				]
  			}
  		},
		methods: {
			showClassData (){
				this.showClass = !this.showClass;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			showMaterialsData (){
				this.showMaterials = !this.showMaterials;
				this.showClass =  false;
				this.showSeries = false;
				this.showStyle = false;
			},
			showSeriesData (){
				this.showSeries = !this.showSeries;
				this.showClass =  false;
				this.showMaterials = false;
				this.showStyle = false;
			},
			showStyleData (){
				this.showStyle = !this.showStyle;
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
			},
			closeBtn (){
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			getPositionIdProdList (positionId){
				this.positionId = positionId;
				this.typeId = null;	
				this.textureId = null;	
				this.seriesId = null;	
				this.styleId = null;
				this.orderByTime = 0;
				this.orderByPageViewsCount = 0;
				this.orderByPrice = 0;
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;
				}).catch((error) => {
					console.log(error)
				})
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			getClassIdProdList (typeId){
				this.typeId = typeId;
				this.textureId = null;	
				this.seriesId = null;	
				this.styleId = null;
				this.orderByTime = 0;
				this.orderByPageViewsCount = 0;
				this.orderByPrice = 0;
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;
				}).catch((error) => {
					console.log(error)
				})
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			getTextureIdProdList (textureId){
				this.textureId = textureId;
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;
				}).catch((error) => {
					console.log(error)
				})
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			getSeriesIdProdList (number){
				this.seriesId = number;
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;

				}).catch((error) => {
					console.log(error)
				})
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			getStyleIdProdList (number){
				this.styleId = number;
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;

				}).catch((error) => {
					console.log(error)
				})
				this.showClass =  false;
				this.showMaterials = false;
				this.showSeries = false;
				this.showStyle = false;
			},
			getOrderByTimeProdList (number){
				this.orderByPageViewsCount = 0;
				this.orderByPrice = 0;
				if ( this.orderByTime == 0 ) {
					this.orderByTime = 1;
				} else {
					this.orderByTime =0
				}
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;

				}).catch((error) => {
					console.log(error)
				})
			},
			getOrderByPageViewsCountProdList (number){
				this.orderByTime = 0;
				this.orderByPrice = 0;
				if ( this.orderByPageViewsCount == 0 ) {
					this.orderByPageViewsCount = 1;
				} else {
					this.orderByPageViewsCount =0;
				}
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;

				}).catch((error) => {
					console.log(error)
				})
			},
			getOrderByPriceProdList (number){
				this.orderByTime = 0;
				this.orderByPageViewsCount = 0;
				if ( this.orderByPrice == 0 ) {
					this.orderByPrice = 1;
				} else {
					this.orderByPrice =0
				}
				let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
				axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/1/12`,dataJson).then((response) => {
					this.prodListData = response.data.list;
					this.total = response.data.total;
				}).catch((error) => {
					console.log(error)
				})
			},
			getMoreProdList (currentPage){
				this.currentPage ++;
            	let dataJson = qs.stringify({
					positionId: this.positionId, 
					typeId : this.typeId,	
					textureId : this.textureId,	
					seriesId : this.seriesId,	
					styleId : this.styleId,		
					orderByTime: this.orderByTime, 
					orderByPageViewsCount: this.orderByPageViewsCount, 
					orderByPrice: this.orderByPrice 
				});
		       // ajax请求, 向后台发送 currentPage, 来获取对应的数据
		        axios.post(`${this.$store.state.wordpressAPI}/product/selectByCondition/${this.currentPage}/12`,dataJson)
		                .then((response)=> {
							let newList = response.data.list;
							this.prodListData.push(...newList);
		                })
		                .catch(function (error) {
		                 	console.log(error);
		                });
		    }
		},
  		validata ({ params }){
			return /^\d+$/.test(params.typeId)
		},
  		async asyncData ({params,query,store}){
			//banner
			let banner = await axios(`${store.state.wordpressAPI}/banner/selectAllByTpye/11`);
			//筛选条件
			let selectData = await axios(`${store.state.wordpressAPI}/proCategory/showAll/list`);
			//列表展示
			let dataJson = qs.stringify({
						   		positionId:params.typeId,
								typeId : query.classId,
								textureId : query.textureId,
								seriesId : null,
								styleId : null,
								orderByTime:0, //是否根据时间排序，1代表是，0代表否
								orderByPageViewsCount:0, //是否销量排序，1代表是，0代表否
								orderByPrice:0 //是否根据价格排序，1代表是，0代表否
							});
			let prodListData = await axios.post(`${store.state.wordpressAPI}/product/selectByCondition/1/12`, dataJson);
			return {
				bannerData: banner.data,
				materialsData: selectData.data[0],  //家具材质
				seriesData: selectData.data[1],		//家具系列
				styleData: selectData.data[2],		//家具风格
				prodListData: prodListData.data.list,
				total: prodListData.data.total
			}
  		},
  		components: {
  			commonBanner,
			prodListShow
  		}
  	} 
</script>

<style scoped>
		div#products-content {
			width:  100%;
			padding: 1.36rem 0;
		}

		div#products-show {
			width:  100%;
		}

		.products-show-box {
			width: 100%;
			padding-top: 0.27rem 0;
		}

		div#products-select {
			width: 100%;
		}

		.products-select-box {
			position:  relative;
			width: 100%;
		}

		.furniture-place {
			width: 100%;
			padding: 0 0.3rem;
			border-top: 0.027rem solid #a0a0a0;
			border-bottom: 0.027rem solid #a0a0a0;
			box-sizing:  border-box;
		}

		.furniture-place-kinds {
			width: 100%;
		}

		.furniture-place-kinds ul {
			display:  flex;
			width: 100%;
			justify-content:  center;
			align-items:  center;
			flex-wrap:  wrap;
		}

		li.furniture-place-kinds-list {
			height: 1.547rem;
			padding: 0 0.373rem;
			font-size: 0.373rem;
			line-height: 1.547rem;
			color: #979797;
		}

		div#products-select {
			width: 100%;
		}

		.products-select-box {
			position:  relative;
			width: 100%;
		}

		.furniture-place {
			width: 100%;
			padding: 0 0.3rem;
			border-top: 0.027rem solid #a0a0a0;
			border-bottom: 0.027rem solid #a0a0a0;
			box-sizing:  border-box;
		}

		.furniture-place-kinds {
			width: 100%;
		}

		.furniture-place-kinds ul {
			display:  flex;
			width: 100%;
			justify-content:  center;
			align-items:  center;
			flex-wrap:  wrap;
		}

		li.furniture-place-kinds-list {
			height: 1.547rem;
			padding: 0 0.373rem;
			font-size: 0.373rem;
			line-height: 1.547rem;
			color: #979797;
		}

		.furniture-class {
			position: absolute;
			top: 1.601rem;
			right: 0;
			left: 0;
			width:  100%;
			height: 49.7rem;
			background: rgba(0,0,0,0.4);
			z-index: 666;
		}

		.furniture-class-kinds {
			width: 100%;
			padding: 0 0.3rem;
			box-sizing: border-box;
			background-color: #fff;
		}

		.furniture-class-kinds ul {
			display:  flex;
			justify-content:  center;
			align-items:  center;
			flex-wrap:  wrap;
		}

		li.furniture-class-kinds-list {
			min-width: 25%;
			height: 0.867rem;
			padding: 0 0.12rem;
			box-sizing:  border-box;
			font-size: 0.32rem;
			text-align:  center;
			line-height: 0.867rem;
			color: #858585;
		}

		li.furniture-class-kinds-list a {
			display:  block;
			width:  100%;
			height: 100%;
			font-size: 0.32rem;
			text-align:  center;
			line-height: 0.867rem;
			color: #858585;
		}

		.furniture-close-box {
			display:  flex;
			width: 100%;
			height: 0.947rem;
			background-color: #f5f5f5;
			justify-content:  center;
			align-items:  center;
		}

		.furniture-close {
			width: 0.6rem;
			height: 0.6rem;
			background-color: rgba(191, 191, 191, 0.68);
			border-radius: 50%;
			color:  #fff;
			text-align:  center;
			line-height:  0.6rem;
			font-size: 0.36rem;
		}

		.products-sequence {
			overflow:  hidden;
			display:  flex;
			width:  100%;
			height: 1.32rem;
			padding: 0 0.3rem;
			box-sizing:  border-box;
			justify-content:  center;
			align-items:  center;
		}

		.products-sequence>div {
			width: 33%;
			height:  100%;
			font-size: 0.32rem;
			text-align:  center;
			line-height: 1.32rem;
			color: #858585;
		}

		li.news-products-list.active {
			color: #000;
		}

		li.products-prices-list.active {
			color: #000;
		}

		.furniture-class-kinds-list.active {
			color: #000;
		}
		/*products-pagination start*/
			div#products-pagination {
			    width:  100%;
			    height:  auto;
			}

			div#products-more-box {
				width:  100%;
			}

			.products-more {
				width: 9.267rem;
				height: 1.067rem;
				margin:  0 auto;
				background-color: #f5f5f5;
				font-size: 0.373rem;
				line-height: 1.067rem;
				text-align: center;
				color: #4b4b4b;
			}
		/*products-pagination end*/
	/*Products select end*/

</style>