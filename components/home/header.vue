<template>
	<header class="v-header">
		<div id="index-header">
			<div class="index-header-box">
				<div class="i-h-nav">
					<div class="phone-show-menu" @click="showMenu">
						<div class="phone-open-menu" v-if="!menuShow">
							<p></p>
							<p></p>
						</div>
						<div class="phone-close-menu" v-if="menuShow"></div>
					</div>	
							
				</div>
				<div class="h-t-logo">
					<nuxt-link to="/">
						<img src="~/assets/images/index/TThome-logo.png" alt="卫诗理">
					</nuxt-link>
				</div>
				<div class="h-t-my">
					<img src="~/assets/images/index/person_center.png" alt="卫诗理">
				</div>
			</div>
			<ul class="h-nav-list" v-show="menuShow"  @click="showMenu">
				<li><nuxt-link to="/">首页</nuxt-link></li>
				<li>
					<nuxt-link to="/brand">品牌故事</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/leader">创始人说</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/experice">体验馆</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/products">产品介绍</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/news">新闻资讯</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/join">招商加盟</nuxt-link>
				</li>						
				<li>
					<nuxt-link to="/service/contact">服务中心</nuxt-link>
				</li>
			</ul>
		</div>
	</header>
	
</template>

<script>
	import { mapState } from 'vuex'

	export default{
		name: 'VHeader',
		data (){
			return {
				menuShow: false
			}
		},
		computed: {
			...mapState(['headProdNav','headNewsNav','headJobNav'])
		},
		mounted (){
			
		},
		methods: {
			showMenu (){
				this.menuShow = !this.menuShow;
			}
		},
		destroyed (){
			window.removeEventListener('scroll',this.handleScroll)
		}
	}
</script>

<style scoped>
	.v-header {
		width:  100%;
		height: 1.987rem;
		background: #fff;
	}

	div#index-header {
		position: fixed;
		top: 0;
		left: 0;
		width:  100%;
		height: 1.987rem;
		z-index: 10086;
		background: #fff;
	}
	.index-header-box {
		display:  flex;
		height: 1.987rem;
		padding: 0 0.413rem;
		justify-content: space-between;
		align-items: center;
		box-sizing:  border-box;
	}

	.i-h-nav {
		width:  0.453rem;
	}

	.h-t-logo {
		width: 1.053rem;
		height: 1.08rem;
	}

	.h-t-logo a {
		display:  block;
		width:  100%;
		height:  100%;
	}

	.h-t-logo a img {
		width:  100%;
		height:  100%;
	}

	.h-t-my {
		width: 0.573rem;
		height: 0.733rem;
	}

	.h-t-my img {
		width:  100%;
	}

	.phone-show-menu {
		width:  100%;
	}

	.phone-open-menu {
		overflow:  hidden;
		width:  100%;
	}

	.phone-open-menu p {
		width: 0.453rem;
		height: 0.04rem;
		margin-top: 0.147rem;
		background-color: #a2a1a2;
	}

	.phone-close-menu {
		width: 0.333rem;
		height: 0.333rem;
		background: url('~/assets/images/index/close_menu.png') center center no-repeat;
	}

	.phone-close-menu {
		width: 0.333rem;
		height: 0.333rem;
	}

	ul.h-nav-list {
		position:  fixed;
		top: 1.987rem;
		left: 0;
		width:  100%;
		height:  100%;
		padding: 0 1.133rem;
		background: #fff;
		box-sizing: border-box;
		z-index: 10080;
	}

	ul.h-nav-list li {
		display:  block;
		width:  100%;
		height:  1.2rem;
		border-bottom: 0.013rem solid #bfbfbf;
	}

	ul.h-nav-list li a {
		display:  block;
		width:  100%;
		height:  100%;
		color: #6d6d6d;
		font-size: 0.373rem;
		line-height:  1.2rem;
		text-align:  left;
	}

</style>