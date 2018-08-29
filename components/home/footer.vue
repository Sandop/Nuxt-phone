<template>
	<footer class="v-footer">
		<div id="index-footer">
			<div class="index-footer-box">
				<div class="footer-logo-box">
					<div class="footer-logo">
						<nuxt-link to="/">
							<img src="~/assets/images/index/footer-logo.png">
						</nuxt-link>
					</div>
					<div class="footer-phone">
						<img src="~/assets/images/index/footer-phone.png">
					</div>
				</div>
				<div class="footer-nav-box">
					<div class="footer-nav">
						<div class="footer-nav-wrap">
							<div class="footer-nav-title" @click="changeShow1">
								<span class="prod-link-title-word">品牌故事</span>
								<span class="prod-link-mark">
									<span class="prod-link-minus" v-show="!changeShowBool1">+</span>
									<span class="prod-link-add" v-show="changeShowBool1">x</span>
								</span>
							</div>
							<div class="footer-nav-list-box" v-show="changeShowBool1">
								<ul class="footer-nav-child">
									<li class="footer-nav-child-list"><nuxt-link to="/brand#brand-story">品牌故事</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/brand#brand-background">品牌背景</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/brand#brand-development">发展历程</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/brand#brand-concept">品牌理念</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/brand#brand-strength">品牌荣誉</nuxt-link></li>
								</ul>
							</div>
						</div>
						<div class="footer-nav-wrap">
							<div class="footer-nav-title" @click="changeShow2">
								<span class="prod-link-title-word">新闻资讯</span>
								<span class="prod-link-mark">
									<span class="prod-link-minus" v-show="!changeShowBool2">+</span>
									<span class="prod-link-add" v-show="changeShowBool2">x</span>
								</span>
							</div>
							<div class="footer-nav-list-box" v-show="changeShowBool2">
								<ul class="footer-nav-child">
									<li v-for="(item,index) in headNewsNav" :key="index" class="footer-nav-child-list">
										<nuxt-link :to="{name: 'news-category',params: {category: item.articleCategoryId}}">{{item.articleCategoryName}}</nuxt-link>
									</li>
								</ul>
							</div>
						</div>

						<div class="footer-nav-wrap">
							<div class="footer-nav-title" @click="changeShow3">
								<span class="prod-link-title-word">产品介绍</span>
								<span class="prod-link-mark">
									<span class="prod-link-minus" v-show="!changeShowBool3">+</span>
									<span class="prod-link-add" v-show="changeShowBool3">x</span>
								</span>
							</div>
							<div class="footer-nav-list-box" v-show="changeShowBool3">
								<ul>
									<li class="footer-nav-child-list">
										<nuxt-link to="/products/newPro">最新产品</nuxt-link>
									</li>
									<li v-for="(item,index) in headProdNav" :key="index" class="footer-nav-child-list" v-if="item.proCategoryId != 96 && item.proCategoryId != 97" >
										<nuxt-link :to="{name: 'products-typeId',params: {typeId: item.proCategoryId}}">{{item.proCategoryName}}</nuxt-link>
									</li>
								</ul>
							</div>
						</div>

						<div class="footer-nav-wrap">
							<div class="footer-nav-title" @click="changeShow4">
								<span class="prod-link-title-word">服务中心</span>
								<span class="prod-link-mark">
									<span class="prod-link-minus" v-show="!changeShowBool4">+</span>
									<span class="prod-link-add" v-show="changeShowBool4">x</span>
								</span>
							</div>
							<div class="footer-nav-list-box" v-show="changeShowBool4">
								<ul class="footer-nav-child">
									<li class="footer-nav-child-list"><nuxt-link to="/service/presales">售前服务</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/service/aftersales">售后服务</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/service/contact">联系我们</nuxt-link></li>
									<li class="footer-nav-child-list"><nuxt-link to="/service/questions">常见问题</nuxt-link></li>
								</ul>
							</div>
						</div>
					</div>
					<div class="footer-code">
						<div class="footer-weixin-box">
							<div class="footer-weixin-code">
								<img src="~/assets/images/index/footer-weixin-code.png">
							</div>
							<div class="footer-weixin-word">扫码关注微信</div>
						</div>
					</div>
				</div>
				<div class="footer-bottom">
					<p>Copyright © 2018 卫诗理家具版权所有</p>
					<p>粤ICP备16080000号-2</p>
					<p><a href="/sitemap">网站地图</a></p>
				</div>
			</div>
		</div>
	</footer>
</template>

<script>
	import { mapState } from 'vuex'

	export default {
		name: 'VFooter',
		data (){
			return {
				changeShowBool1:false,
				changeShowBool2:false,
				changeShowBool3:false,
				changeShowBool4:false,
			}
		},
		computed: {
			...mapState(['headProdNav','headNewsNav'])
		},
		methods: {
			changeShow1 (){
				this.changeShowBool1 = !this.changeShowBool1;
				this.changeShowBool2 = false;
				this.changeShowBool3 = false;
				this.changeShowBool4 = false;
			},
			changeShow2 (){
				this.changeShowBool2 = !this.changeShowBool2;
				this.changeShowBool1 = false;
				this.changeShowBool3 = false;
				this.changeShowBool4 = false;
			},
			changeShow3 (){
				this.changeShowBool3 = !this.changeShowBool3;
				this.changeShowBool2 = false;
				this.changeShowBool1 = false;
				this.changeShowBool4 = false;
			},
			changeShow4 (){
				this.changeShowBool4 = !this.changeShowBool4;
				this.changeShowBool2 = false;
				this.changeShowBool3 = false;
				this.changeShowBool1 = false;
			}
		}
	}
</script>

<style scoped>
	footer.v-footer {
		width:  100%;
		background-color: #3e3f43;
	}

	.index-footer-box {
		width:  100%;
	}

	.footer-logo-box {
		display:  flex;
		width:  100%;
		height:  1.52rem;
		padding: 0 2%;
		justify-content:  space-between;
		align-items:  center;
		border-bottom: 0.027rem solid rgba(249, 249, 250,0.1);
		box-sizing:  border-box;
	}

	.footer-logo-box img {
		transform: scale(0.7);
	}

	.footer-nav-box {
		width:  100%;
		padding: 0.907rem 0.627rem 0 0.64rem;
		box-sizing:  border-box;
	}

	.footer-nav {
		width:  100%;
	}

	.footer-nav-wrap {
		width: 100%;
		border-bottom: 0.027rem solid rgba(249, 249, 250, .1);
	}

	.footer-nav-title {
		width:  100%;
		height:  1.173rem;
		box-sizing:  border-box;
		color:  #fff;
		font-size: 0.373rem;
		line-height: 1.173rem;
	}

	span.prod-link-mark {
		float:  right;
		margin-right: 5%;
	}

	.footer-nav-list-box {
		width:  100%;
		padding-bottom: 0.36rem;
	}

	ul.footer-nav-child {
		width:  100%;
	}

	li.footer-nav-child-list {
		width:  100%;
		height: 0.68rem;
	}

	li.footer-nav-child-list a {
		display:  block;
		width:  100%;
		height:  100%;
		overflow:  hidden;
		font-size: 0.293rem;
		line-height: 0.68rem;
		color: #969696;
	}

	.footer-code {
		width:  100%;
		padding: 1.04rem 0 1.173rem;
		text-align:  center;
	}

	.footer-weixin-box {
		width:  100%;
	}

	.footer-weixin-code {
		overflow:  hidden;
		width: 1.8rem;
		height: 1.8rem;
		margin:  0 auto;
	}

	.footer-weixin-code img {
		width:  100%;
		height: 100%;
	}

	.footer-weixin-word {
		margin-top: 0.067rem;
		font-size: 0.259rem;
		line-height: 0.293rem;
		color: #ffffff;
	}

	.footer-bottom {
		width:  100%;
		text-align:  center;
		padding-bottom:  0.8rem;
	}

	.footer-bottom p {
		height: 0.507rem;
		font-size: 0.24rem;
		line-height: 0.507rem;
		color: #696969;
	}

	.footer-bottom a {
		color: #696969;
	}
</style>