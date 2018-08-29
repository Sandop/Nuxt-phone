<template>
    <div id="experice_design">
        <div class="experice_design_box">
            <div class="experice_design_title">
                <div class="experice_design_titleC"><h2>分馆介绍</h2></div>
                <p class="experice_design_titleE">For what service</p>
            </div>
            <div class="experice_design_content_box">
                <div class="experice_design_place_container">
                    <div class="experience_tab_content">
                        <div class="experience_tab_box" v-show="currentNum == 0" @mouseenter="stop" @mouseleave="go">
                            <div class="experice_design_place_box clearfix">
                                <div class="experice_design_place">包头</div>
                                <div class="experice_design_place_line"></div>
                                <div class="experice_design_place_intro">卫诗理Olivelife新零售包头店</div>
                            </div>
                            <div class="experice_design_place_desc">
                                <p class="experice_design_place_descC">卫诗理Olive life 新零售包头店，逐梦之路，未来之巅</p>
                                <p class="experice_design_place_descE">The road to the dream,the top of the future</p>
                            </div>
                            <div class="experice_design_place_img_box">
                                <div class="experice_design_place_img"><img src="~/assets/images/experice/experice_design_place_img1.png"></div>
                                <div class="experice_design_place_img_desc">
                                    <p>地址：包头市青山区传媒大厦B座117卫诗理包头店</p>
                                    <p>营业时间：9：00-18：00</p>
                                </div>
                            </div>
                            <div class="experice_design_place_more">
                                <nuxt-link to="/experice/bt">了解更多 ></nuxt-link>
                            </div>
                        </div>
                        <div class="experience_tab_box" v-show="currentNum == 1" @mouseenter="stop" @mouseleave="go">
                            <div class="experice_design_place_box clearfix">
                                <div class="experice_design_place">成都</div>
                                <div class="experice_design_place_line"></div>
                                <div class="experice_design_place_intro">卫诗理新零售成都“卫志”店 </div>
                            </div>
                            <div class="experice_design_place_desc">
                                <p class="experice_design_place_descC">卫诗理新零售成都“卫志”店，生态生活，盎然新启</p>
                                <p class="experice_design_place_descE">Olivelife,opens the door of a new world</p>
                            </div>
                            <div class="experice_design_place_img_box">
                                <div class="experice_design_place_img"><img src="~/assets/images/experice/experice_design_place_img2.png"></div>
                                <div class="experice_design_place_img_desc">
                                    <p>地址：成都市武侯区首信红星国际广场1号楼卫诗理家具旗舰店</p>
                                    <p>营业时间：9：00-18：00</p>
                                </div>
                            </div>
                            <div class="experice_design_place_more">
                                <nuxt-link to="/experice/cd">了解更多 ></nuxt-link>
                            </div>
                        </div>
                        <div class="experience_tab_box" v-show="currentNum == 2" @mouseenter="stop" @mouseleave="go">
                            <div class="experice_design_place_box clearfix">
                                <div class="experice_design_place">南京</div>
                                <div class="experice_design_place_line"></div>
                                <div class="experice_design_place_intro">卫诗理 线下O2O南京“卫共”店 </div>
                            </div>
                            <div class="experice_design_place_desc">
                                <p class="experice_design_place_descC">初心不移，呈现生活最美的姿态</p>
                                <p class="experice_design_place_descE">Pure European noble experience , giving noble new definition</p>
                            </div>
                            <div class="experice_design_place_img_box">
                                <div class="experice_design_place_img"><img src="~/assets/images/experice/experice_design_place_img3.png"></div>
                                <div class="experice_design_place_img_desc">
                                    <p>地址：南京市建邺区水西门大街285号289号万达金街东区</p>
                                    <p>营业时间：9：00-18：00</p>
                                </div>
                            </div>
                            <div class="experice_design_place_more">
                                <nuxt-link to="/experice/nj">了解更多 ></nuxt-link>
                            </div>
                        </div>
                        <div class="experience_tab_box" v-show="currentNum == 3" @mouseenter="stop" @mouseleave="go">
                            <div class="experice_design_place_box clearfix">
                                <div class="experice_design_place">东莞</div>
                                <div class="experice_design_place_line"></div>
                                <div class="experice_design_place_intro">卫诗理Olivelife生态生活体验馆</div>
                            </div>
                            <div class="experice_design_place_desc">
                                <p class="experice_design_place_descC">纯正欧式尊贵体验，赋予贵族新的定义</p>
                                <p class="experice_design_place_descE">Pure European noble experience, giving noble new definition</p>
                            </div>
                            <div class="experice_design_place_img_box">
                                <div class="experice_design_place_img"><img src="~/assets/images/experice/experice_design_place_img4.png"></div>
                                <div class="experice_design_place_img_desc">
                                    <p>地址：东莞市厚街家具大道209号</p>
                                    <p>营业时间：9：00-18：00</p>
                                </div>
                            </div>
                            <div class="experice_design_place_more">
                                <nuxt-link to="/experice/dg">了解更多 ></nuxt-link>
                            </div>
                        </div>
                    </div>
                    <ul class="experience_dot_nav">
                        <li class="experience_dot" v-for="(list,index) in experienceDot" :key="index" :class="{active: index == currentNum}" @click="tabIndex(index)" @mouseenter="stop" @mouseleave="go"></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "expericeDesign",
    data (){
        return {
            currentNum: 0,
            experienceDot: ['','','',''],
            timer: ''
        }
    },
    created (){
        //在dom加载完成后下个tick中开始轮播
        this.$nextTick(()=>{
            this.timer = setInterval(() => {
                this.autoPlay()
            },3000)
        });
    },
    methods: {
        tabIndex (index){
            this.currentNum =index;
        },
        autoPlay (){
            let length = this.experienceDot.length;
            this.currentNum ++;
            if (this.currentNum > length-1) {
                this.currentNum = 0;
            }
        },
        go (){
            this.timer = setInterval(() => {this.autoPlay()},3000)
        },
        stop (){
            clearInterval (this.timer);
            this.timer = null;
        }
    }
}
</script>

<style scoped>
	div#experice_design {
		width:  100%;
		background: #f9f9fa;
	}

	.experice_design_box {
		width:  100%;
	}

	.experice_design_title {
		width:  100%;
		padding: 1.32rem 0 0.88rem;
		text-align: center;
	}

	.experice_design_titleC {
		height: 0.613rem;
		font-size: 0.64rem;
		font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
		font-weight: 900;
		color: #22202b;
		line-height: 0.613rem;
	}

	p.experice_design_titleE {
		width: 100%;
		height: 0.24rem;
		margin-top: 0.107rem;
		font-size: 0.187rem;
		line-height: 0.24rem;
		color: #858585;
	}

	.experice_design_content_box {
		width:  100%;
		text-align: center;
	}

	.experice_design_place_container {
		position:  relative;
		width:  100%;
	}

	.experience_tab_content {
		width:  100%;
		padding-bottom: 1.32rem;
	}

	.experience_tab_box {
		width:  100%;
	}

	.experice_design_place_box {
		width:  100%;
	}

	.experice_design_place {
		font-family: MicrosoftYaHei-Bold;
		font-size: 0.373rem;
		font-weight: bold;
		line-height: 0.45rem;
		color: #22202b;
	}

	.experice_design_place_intro {
		font-family: AdobeHeitiStd-Regular;
		font-size: 0.32rem;
		line-height: 0.5rem;
		color: #22202b;
	}

	.experice_design_place_desc {
		width:  100%;
		padding: 0.827rem 0 1.027rem;
	}

	p.experice_design_place_descC {
		font-family: AdobeHeitiStd-Regular;
		font-size: 0.32rem;
		line-height: 0.45rem;
		color: #858585;
	}

	p.experice_design_place_descE {
		font-family: AdobeHeitiStd-Regular;
		font-size: 0.24rem;
		line-height: 0.45rem;
		color: #cccccc;
	}

	.experice_design_place_img_box {
		width: 9.213rem;
		margin:  0 auto;
	}

	.experice_design_place_img {
		overflow:  hidden;
		width: 9.213rem;
		height: 5.6rem;
	}

	.experice_design_place_img img {
		width:  100%;
	}

	.experice_design_place_img_desc {
		width:  100%;
		padding-top: 1.413rem;
	}

	.experice_design_place_img_desc p {
		font-size: 0.32rem;
		line-height: 0.477rem;
		color: #858585;
	}

	.experice_design_place_more {
		margin-top: 0.8rem;
	}

	.experice_design_place_more a {
		display:  block;
		width:  100%;
		font-family: MicrosoftYaHei-Bold;
		font-size: 0.32rem;
		font-weight: bold;
		line-height: 0.45rem;
		color: #22202b;
	}
	
	ul.experience_dot_nav {
		position:  absolute;
		bottom:  31%;
		left:  0;
		width:  100%;
	}	

	li.experience_dot {
		display:  inline-block;
		width: 0.2rem;
		height: 0.2rem;
		margin: 0 0.11rem;
		background-color: #858585;
		border-radius: 50%;
	}

	li.experience_dot.active {
		background-color: #22202b;
	}
		
</style>


