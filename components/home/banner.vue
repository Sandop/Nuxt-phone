<template>
	<div id="index-banner">
		<div class="i-b-container">
			<transition-group tag="div" class="part-box" name="listNext" v-show="isLeft">
				<div class="b-c-part" v-for="(list,index) in bannerData" :key="index" v-show="index === currentIndex" @mouseenter="stop" @mouseleave="go">
					<a :href="`${list.href}`" target="_blank" :rel="list.ref">
						<img :src="list.bannerSrc" :alt="list.bannerAlt">
					</a>
				</div>
			</transition-group>
			<transition-group tag="div" class="part-box" name="listPrev" v-show="!isLeft">
				<div class="b-c-part" v-for="(list,index) in bannerData" :key="index" v-show="index === currentIndex" @mouseenter="stop" @mouseleave="go">
					<a :href="`${list.href}`" target="_blank" :rel="list.ref">
						<img :src="list.bannerSrc" :alt="list.bannerAlt">
					</a>
				</div>
			</transition-group>
		</div>

		<div class="i-b-tab">
			<ul>
				<li v-for="(item,index) in bannerData" :key="index" :class="{active: index === currentIndex}" @click="change(index)"></li>
			</ul>
		</div>
		<div class="i-b-btn">
			<div class="btn-pre" @click="prev" @mouseenter="stop" @mouseleave="go"></div>
			<div class="btn-next" @click="next" @mouseenter="stop" @mouseleave="go"></div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'VBanner',
		props:{
			//bannerData，里面的data属性包含着图片的数组
			bannerData: {
				type:Array,
				required:true
			}
		},
		data (){
			return {
				isLeft:true,
				currentIndex: 0,
				timer: '',
				clickTime: 0
			}
		},
		created (){
			//在DOM加载完成后，下个tick中开始轮播
			this.$nextTick(()=>{
				this.timer = setInterval(()=>{
					this.autoPlay()
				},4000)
			});
		},
		methods: {
			go (){
				this.timer = setInterval(()=>{
					this.autoPlay()
				},4000)
			},
			stop (){
				clearInterval(this.timer);
				this.timer = null;
			},
			change (index){
				this.currentIndex = index;
			},
			autoPlay (){
				this.isLeft = true;
				this.currentIndex ++;
				if (this.currentIndex > this.bannerData.length - 1) {
					this.currentIndex = 0;
				}
			},
			prev (){
				if (new Date() - this.clickTime > 850) {
					this.isLeft = false;
					this.currentIndex --;
					if (this.currentIndex < 0) {
						this.currentIndex = this.bannerData.length - 1;
					}

					this.clickTime = new Date();
				}
				
			},
			next (){
				if (new Date() - this.clickTime > 850) {
					this.isLeft = true;
					this.currentIndex ++;
					if (this.currentIndex > this.bannerData.length - 1) {
						this.currentIndex = 0;
					}

					this.clickTime = new Date();
				}

				
			}
		}
	}
</script>

<style scoped>
	#index-banner {
	    position:  relative;
	    overflow:  hidden; 
	    width:  100%;
	    height:  auto;
	}

	.part-box {
		width:  100%;
		height:  100%;
	}

	.i-b-container {
	    position:  relative;
	    width: 100%;
	    height:  10.667rem;
	    margin:  0 auto;
	}

	.i-b-tab {
	    width: 100%;
	    height: 0.227rem;
	    margin-top: 0.213rem;
		text-align: center;
	}

	.i-b-tab ul {
		width: 100%;
		height: 100%;
	}

	.i-b-tab ul li {
		display: inline-block;
		width: 0.227rem;
		height: 0.227rem;
		margin: 0 0.106rem;
		background-color: #e5e5e5;
		border-radius: 50%;
	}

	.i-b-tab ul li.active {
		background-color: #7d7d7d;
	}

	.b-c-part {
	    position:  absolute;
	    overflow:  hidden;
	    width: 100%;
	    height:  100%;
	}

	.b-c-part a {
		position: relative;
		display: block;
		overflow: hidden;
		width: 100%;
		height: 100%;
	}

	.b-c-part a img {
	    overflow:  hidden;
		width: 100%;
		height: 100%;
	}

	.i-b-btn {
	    position:  relative;
	    width:  1200px;
	    margin: 0 auto;
	}

	.btn-pre {
	    display: none;
	}

	.btn-next {
	    display: none;
	}

	.listNext-enter-to {
	  transition: all 1s ease;
	  transform: translateX(0);
	}

	.listNext-leave-active {
	  transition: all 1s ease;
	  transform: translateX(-100%)
	}

	.listNext-enter {
	  transform: translateX(100%)
	}

	.listNext-leave {
	  transform: translateX(0)
	}

	.listPrev-enter-to {
	  transition: all 1s ease;
	  transform: translateX(0);
	}

	.listPrev-leave-active {
	  transition: all 1s ease;
	  transform: translateX(100%)
	}

	.listPrev-enter {
	  transform: translateX(-100%)
	}

	.listPrev-leave {
	  transform: translateX(0)
	}
</style>