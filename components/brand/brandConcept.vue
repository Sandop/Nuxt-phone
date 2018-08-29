<template>
    <div id="brand-concept">
        <div class="concept-content">
            <div class="concept-content-top">
                <div class="concept-content-top-titleC"><h2>品牌宗旨</h2></div>
                <div class="concept-content-top-titleE">Brand purpose</div>
                <div class="concept-content-top-description">以家庭为单位、一孩子为主体</div>
            </div>
            <div class="concept-content-box">
                <div class="concept-intro">
                    <div class="concept-intro-left">
                        <img src="~/assets/images/brand/concept-intro.png">
                    </div>
                    <div class="concept-intro-right">
                        <div class="concept-intro-title">
                            “以家庭为单位、以孩子为主体”
                        </div>
                        <div class="concept-intro-content">
                            <p>全方位为全球家庭提供高雅、高品位、轻奢、绿色、健康、舒适的理想居家环境，为中高端客户提供高端服务和整体家空间的打造：包括软装、硬装、全屋定制、家具定制、园林、花艺、高端礼服定制、婚宴、生日、庆典、现场布置等一体化家居服务。</p>
                        </div>
                    </div>
                </div>
                <div class="concept-details">
                    <div class="concept-details-right">
                        <div class="concept-details-video">
                            <indexVideo></indexVideo>
                        </div>
                    </div>
                    <div class="concept-details-left">
                        <div class="brand-slogan">
                            <p class="brand-concept-title">品牌口号</p>
                            <p class="brand-concept-desc">生活多点仪式感！</p>
                        </div>
                        <div class="brand-slogan">
                            <p class="brand-concept-title">品牌定位</p>
                            <p class="brand-concept-desc">一个家庭的高级服务管家，一个生活的居家美学顾问</p>
                        </div>
                        <div class="brand-slogan">
                            <p class="brand-concept-title">品牌使命</p>
                            <p class="brand-concept-desc">通过美学教育和生活礼仪，让孩子获得更美好的未来</p>
                        </div>
                        <div class="brand-slogan">
                            <p class="brand-concept-title">品牌愿景</p>
                            <p class="brand-concept-desc">打造家居+生活一站式服务平台</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
	import indexVideo from '~/components/home/indexVideo'
    export default {
        name: 'brandConcept',
        components: {
			indexVideo
        }
    }
</script>
<style>
    div#brand-concept {
        width:  100%;
        background: #f9f9fa;
    }

    .concept-content {
        width: 100%;
        padding:  0 0.84rem;
        box-sizing:  border-box;
    }

    .concept-content-top {
        width: 100%;
        text-align: center;
        padding-top: 1.333rem;
        padding-bottom: 0.813rem;
    }

    .concept-content-top-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .concept-content-top-titleE {
        width: 100%;
        height: 0.24rem;
        margin-top: 0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    .concept-content-top-description {
        height: 0.32rem;
        margin-top: 0.24rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        font-weight: normal;
        line-height: 0.32rem;
        color: #858585;
    }

    .concept-content-box {
        width:  100%;
    }

    .concept-intro {
        width:  100%;
    }

    .concept-intro-left {
        position:  relative;
        overflow:  hidden;
        width:  100%;
        height: 4.067rem;
    }

    .concept-intro-left img {
        position: absolute;
        top: 50%;
        left: 50%;
        overflow: hidden;
        transform: translate(-50%,-50%) scale(0.74);
    }

    .concept-intro-right {
        width:  100%;
    }

    .concept-intro-title {
        width:  100%;
        height: 2.053rem;
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.4rem;
        font-weight: bold;
        text-align:  left;
        line-height: 2.053rem;
        color: #22202b;
    }

    .concept-intro-content {
        font-size: 0.32rem;
        text-align: left;
        line-height: 0.48rem;
        color: #858585;
    }

    .concept-details {
        width:  100%;
        padding: 1.36rem 0 1.347rem;
    }

    .concept-details-right {
        overflow:  hidden;
        width:  100%;
        height: 4.547rem;
    }

    .concept-details-video {
        width:  100%;
        height:  100%;
    }

    .concept-details-left {
        width:  100%;
        text-align:  center;
    }

    .brand-slogan {
        width:  100%;
        padding-top:  0.853rem;
    }

    p.brand-concept-title {
        font-family: MicrosoftYaHei;
        font-size: 0.4rem;
        line-height: 0.54rem;
        letter-spacing: 0rem;
        color: #6d6d6d;
    }

    p.brand-concept-desc {
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }
</style>


