<template>
	<section class="container">
		<!-- banner -->
      	<commonBanner :bannerSrc="bannerSrc"></commonBanner>
        <div class="new_products_wrap">
            <div class="new_products_box">
                <!-- products-show start -->
                <div id="products-show">
                    <prodListShow :prodList="newProdList" :typeId="97" :showNum="999999999"></prodListShow>
                </div>
                <!-- products-show end -->
                
                <!-- products-pagination start-->
                <div id="products-more-box" @click="getMoreProdList" v-if="newProdList.length < total">
                    <div class="products-more">
						查看更多 >
					</div>
                </div>
				<div class="products-more-box"  v-if="newProdList.length >= total">
					<div class="products-more">
					------我是有底线哒O(∩_∩)O~------
					</div>
				</div>
                <!-- products-pagination end-->
            </div>
        </div>
      	
      	
	</section>
</template>

<script>
	import axios from 'axios'
	import prodListShow from '~/components/common/prodListShow'
	import commonBanner from '~/components/common/commonBanner'
      
	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/join/prodBanner1.jpg',

				currentPage: 1,   // 当前的页数
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
            //新品数据
			let newProdList = await axios.post(`${store.state.wordpressAPI}/product/selectByNew/1/12`);
			return {
				metaData: metaData.data,
                newProdList: newProdList.data.list,
                total: newProdList.data.total
			}
		},
		components: {
			prodListShow,
			commonBanner
        },
        methods: {
            getMoreProdList (){
				this.currentPage ++;
		       // ajax请求, 向后台发送 currentPage, 来获取对应的数据
		        axios.post(`${this.$store.state.wordpressAPI}/product/selectByNew/${this.currentPage}/12`)
		                .then((response)=> {
							let newList = response.data.list;
							this.newProdList.push(...newList);
		                })
		                .catch(function (error) {
		                 	console.log(error);
		                });
			}
		}
	}
</script>

<style type="text/css" scoped>

	.new_products_wrap {
		width:  100%;
	}

	.new_products_box {
		width:  100%;
		margin:  0 auto;
		padding-bottom: 1.133rem;
	}

	div#products-show {
		width:  100%;
		padding: 1.36rem 0 0.26rem;
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
</style>