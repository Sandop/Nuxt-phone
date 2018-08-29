<template>
    <div id="index-story">
        <div class="i-s-contant">
            <div class="s-c-top">
                <div class="c-t-titleC"><h2>品牌故事</h2></div>
                <div class="c-t-titleE">Brand Story</div>
                <div class="c-t-description">爱，一个梦想，一生一世一个家</div>
            </div>
            <div class="s-c-bottom">
                <div class="story-bottom-vedios">
                    <indexVideo></indexVideo>
                </div>
                <div class="story-bottom-detalis">
                    <div class="bottom-detalis-title">
                        <div class="bottom-detalis-titleC">
                            <p class="detalis-titleC-first">我生怕辜负</p>
                            <p class="detalis-titleC-sec">这个时代</p>
                        </div>
                    </div>
                    <div class="bottom-detalis-content">
                        “这是最好的时代，也是最坏的时代”，100年前英国文学家狄更斯这样描述工业革命发生后的时代。如今时代又何尝不是如此呢？阶级被打破，边界在打破，跨界与创新，互联网让世界变得更加平等，每个人都有自己追求梦想的机会，以及成功的可能性......
                    </div>
                    <div class="bottom-detalis-more">
                        <nuxt-link to="/brand">了解更多 ></nuxt-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import indexVideo from '~/components/home/indexVideo'

	export default {
        name: 'indexStory',
        components: {
            indexVideo
        }
	}
</script>

<style scoped>
	.i-b-tab {
        width:  100%;
    }

    div#index-story {
        width:  100%;
    }

    .i-s-contant {
        width:  100%;
    }

    .s-c-top {
        width:  100%;
        text-align:  center;
        padding-top: 1.373rem;
        padding-bottom: 0.947rem;
    }

    .c-t-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','宋体', 'serif';
        font-weight: 900;
        color:  #22202b;
        line-height: 0.613rem;
    }

    .c-t-titleE {
        width:  100%;
        height:  0.24rem;
        margin-top:  0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    .c-t-description {
        height: 0.32rem;
        margin-top: 0.12rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        font-weight: normal;
        line-height: 0.32rem;
        color: #858585;
    }

    .s-c-bottom {
        width:  100%;
    }

    .story-bottom-vedios {
        width:  100%;
        height: 6.707rem;
    }

    .story-bottom-detalis {
        width:  100%;
        padding: 0.787rem 1.533rem 1.307rem 1.293rem;
        box-sizing:  border-box;
    }

    .bottom-detalis-title {
        width:  100%;
        height: 1.013rem;
        font-family: MicrosoftYaHei;
        font-size: 0.48rem;
        font-weight: normal;
        font-stretch: normal;
        line-height: 0.533rem;
        letter-spacing: 0rem;
        color: #22202b;
    }

    .bottom-detalis-titleC {
        position:  relative;
    }


    .bottom-detalis-titleC:after {
        position: absolute;
        top: 50%;
        right: 0;
        content: "";
        width: 4.52rem;
        height: 0.027rem;
        background-color: #d5d5d8;
    }

    .bottom-detalis-content {
        padding-top: 0.64rem;
        padding-bottom: 0.76rem;
        font-size: 0.373rem;
        line-height: 0.453rem;
        color: #858585;
        box-sizing:  border-box;
    }

    .bottom-detalis-more {
        width:  100%;
        height: 0.32rem;
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.32rem;
        line-height: 0.32rem;
        text-align:  center;
    }

    .bottom-detalis-more a {
        color: #22202b;
    }
</style>

