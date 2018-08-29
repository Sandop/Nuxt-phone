<template>
    <div id="index-experience">
        <div class="experience-content">
            <div class="experience-content-top">
                <div class="experience-content-top-titleC"><h2>体验馆</h2></div>
                <div class="experience-content-top-titleE">Experience Stores</div>
                <div class="experience-content-top-description">我们所有的努力，旨在打造一个宾至如归的理想状态</div>
            </div>
            <div class="experience-content-box">
                <div class="experience-place-container">
                    <div class="experience-tab-content">
                        <div class="experience-tab-box experience-tab-box-bt" v-show="0 == num">
                            <div class="experience-tab-left">
                                <div class="experience-tab-left-place">包头</div>
                                <div class="experience-tab-left-img">
                                    <img src="~/assets/images/index/experience-tab-left-img-bt.png">
                                </div>
                            </div>
                            <div class="experience-tab-right">
                                <div class="tab-right-intro">
                                    <div class="tab-right-intro-title">
                                        <p>逐梦</p>
                                        <p>鹿都之巅</p>
                                    </div>
                                    <div class="tab-right-intro-title-desc">卫诗理Olive life 新零售包头店，逐梦之路，未来之巅</div>
                                </div>
                            </div>
                            <div class="tab-right-intro-more">
                                <nuxt-link to="experice/bt">了解更多 ></nuxt-link>
                            </div>
                        </div>
                        <div class="experience-tab-box experience-tab-box-bt" v-show="1 == num">
                            <div class="experience-tab-left">
                                <div class="experience-tab-left-place">成都</div>
                                <div class="experience-tab-left-img">
                                    <img src="~/assets/images/index/experience-tab-left-img-cd.png">
                                </div>
                            </div>
                            <div class="experience-tab-right">
                                <div class="tab-right-intro">
                                    <div class="tab-right-intro-title">
                                        <p>天府之国</p>
                                    </div>
                                    <div class="tab-right-intro-title-desc">卫诗理新零售成都“卫共”店，生态生活，盎然新启</div>
                                </div>
                            </div>
                            <div class="tab-right-intro-more">
                                <nuxt-link to="experice/cd">了解更多 ></nuxt-link>
                            </div>
                        </div>
                        <div class="experience-tab-box experience-tab-box-bt" v-show="2 == num">
                            <div class="experience-tab-left">
                                <div class="experience-tab-left-place">南京</div>
                                <div class="experience-tab-left-img">
                                    <img src="~/assets/images/index/experience-tab-left-img-nanjing.jpg">
                                </div>
                            </div>
                            <div class="experience-tab-right">
                                <div class="tab-right-intro">
                                    <div class="tab-right-intro-title">
                                        <p>绽放</p>
                                        <p>十朝都会</p>
                                    </div>
                                    <div class="tab-right-intro-title-desc">卫诗理线下O2O南京"卫共"店初心不移，呈现生活最美的姿态</div>
                                </div>
                            </div>
                            <div class="tab-right-intro-more">
                                <nuxt-link to="experice/nj">了解更多 ></nuxt-link>
                            </div>
                        </div>
                        <div class="experience-tab-box experience-tab-box-bt" v-show="3 == num">
                            <div class="experience-tab-left">
                                <div class="experience-tab-left-place">东莞</div>
                                <div class="experience-tab-left-img">
                                    <img src="~/assets/images/index/experience-tab-left-img-dg.png">
                                </div>
                            </div>
                            <div class="experience-tab-right">
                                <div class="tab-right-intro">
                                    <div class="tab-right-intro-title">
                                        <p>臻贡</p>
                                        <p>一个阶层</p>
                                    </div>
                                    <div class="tab-right-intro-title-desc">纯正欧式尊贵体验，赋予贵族新的定义</div>
                                </div>
                            </div>
                            <div class="tab-right-intro-more">
                                <nuxt-link to="experice/dg">了解更多 ></nuxt-link>
                            </div>
                        </div>
                    </div>
                    <div class="experience-place-ul-box">
                        <ul class="experience-place-nav">
                            <li class="experience-place" v-for="(item,index) in experiencePlace" :key="index" :class="{active:index == num}" @click="tab(index)">{{item}}</li>
                            <li class="experience-place">武汉</li>
                            <li class="experience-place">杭州</li>
                            <li class="experience-place">深圳</li>
                        </ul>
                    </div>
                    <div class="experience-href"><nuxt-link to="/join">招商加盟详情</nuxt-link></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'indexExperience',
        data (){
            return {
                experiencePlace:['包头','成都','南京','东莞'],
                num:0
            }
        },
        methods: {
            tab (index){
                this.num = index;
            }
        }
    }
</script>

<style>
    div#index-experience {
        width:  100%;
        background-color: #f5f5f5;
    }

    .experience-content-top {
        width: 100%;
        text-align: center;
        padding-top: 1.373rem;
        padding-bottom: 0.947rem;
    }

    .experience-content-top-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .experience-content-top-titleE {
        width: 100%;
        height: 0.24rem;
        margin-top: 0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    .experience-content-top-description {
        height: 0.32rem;
        margin-top: 0.12rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        font-weight: normal;
        line-height: 0.32rem;
        color: #858585;
    }

    .experience-content-box {
        width: 100%;
    }

    .experience-place-container {
        position: relative;
        width: 100%;
        padding-bottom: 2.213rem;
    }

    .experience-tab-content {
        width: 100%;
    }

    .experience-tab-box {
        width: 100%;
    }

    .experience-tab-left {
        width: 100%;
        padding-top: 0.147rem;
        text-align:  center;
    }

    .experience-tab-left-place {
        width: 100%;
        height: 0.48rem;
        font-family: AdobeHeitiStd-Regular;
        font-size: 0.48rem;
        line-height: 0.48rem;
        color: #22202b;
    }

    .experience-tab-left-img {
        position:  relative;
        overflow:  hidden;
        width:  100%;
        height: 4.973rem;
        margin-top: 0.24rem;
    }

    .experience-tab-left-img img {
        position: absolute;
        top: 50%;
        left: 50%;
        overflow: hidden;
        -webkit-transform: translate(-50%,-50%) scale(0.6);
        transform: translate(-50%,-50%) scale(0.5,0.4);
    }

    .experience-tab-right {
        width:  100%;
        padding: 0.8rem 1.6rem 0.84rem 1.213rem;
        box-sizing:  border-box;
    }

    .tab-right-intro {
        width:  100%;
    }

    .tab-right-intro-title {
        position:  relative;
        font-size: 0.48rem;
        line-height: 0.533rem;
        color: #22202b;
    }

    .tab-right-intro-title:after {
        position: absolute;
        top: 50%;
        right: 0;
        content: "";
        width: 4.52rem;
        height: 0.027rem;
        background-color: #d5d5d8;
    }

    .tab-right-intro-title-desc {
        margin-top: 0.107rem;
        font-family: MicrosoftYaHei;
        font-size: 0.267rem;
        line-height: 0.467rem;
        color: #979797;
    }

    .tab-right-intro-more {
        position:  absolute;
        left: 50%;
        bottom: 1.347rem;
        transform: translateX(-50%);
    }

    .tab-right-intro-more a {
        display:  block;
        width:  100%;
        height:  100%;
        font-size: 0.32rem;
        font-family: MicrosoftYaHei-Bold;
        line-height: 0.32rem;
        color: #000000;
    }

    .experience-place-ul-box {
        width:  100%;
        padding-left: 1.1rem;
        padding-right: 1.1rem;
        box-sizing:  border-box;
    }

    ul.experience-place-nav {
        display:  flex;
        width:  100%;
        justify-content:  center;
        align-items:  center;
        flex-wrap: wrap;
    }

    li.experience-place {
        width: 2.347rem;
        height: 1.013rem;
        margin: 0.12rem 0.0865rem;
        border: solid 0.04rem #000000;
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.317rem;
        font-weight: bold;
        text-align: center;
        line-height: 0.933rem;
        color: #000000;
    }

    li.experience-place.active {
        background-color: #000;
        color: #feeabd;
    }

    .experience-href {
        width:  100%;
        height:  auto;
        padding: 0.72rem 0 0.547rem;
        font-size: 0.4rem;
        line-height:  0.387rem;
        text-align:  center;
    }

    .experience-href a {
        display:  block;
        width:  100%;
        height:  100%;
        color:  #858585;
    }
</style>


