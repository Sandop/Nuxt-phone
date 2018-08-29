<template>
    <div id="experice_idea_wrap">
        <div class="experice_idea_box">
            <div class="experice_idea_title">
                <div class="experice_idea_titleC"><h2>建馆理念</h2></div>
                <p class="experice_idea_titleE">The future of smart city and the new retail era</p>
            </div>
            <div class="experice_idea_num_box">
                <div class="experice_idea_img"><img src="~/assets/images/experice/experice_idea_img.png"></div>
                <div class="experice_idea_intro"><p>精诚所至共创未来势，雄心壮志同筑梦想家</p></div>
                <div class="experice_idea_num">
                    <div class="experice_idea_num_desc1">
                        <p class="experice_idea_numbers">18</p>
                        <p>座城</p>
                        <p>每一座都是梦想的承载</p>
                    </div>
                    <div class="experice_idea_num_desc2">
                        <p class="experice_idea_numbers">365</p>
                        <p>家店</p>
                        <p>是梦想之光永不落的象征</p>
                    </div>
                </div>
                <div class="experice_idea_desc">
                    <p>Ⅰ、中国高端家具O2O新零售模式先行者。</p>
                    <p>Ⅱ、联手国际一线大牌设计师，打造生活家居新模式。</p>
                    <p>Ⅲ 、以美为本，创造体验式营销新高度。</p>
                    <p>Ⅳ、整合高端生活方式，打造城市顶级艺术生活综合体。</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'expericeIdea'
    }
</script>

<style>
    div#experice_idea_wrap {
        width:  100%;
    }

    .experice_idea_box {
        width:  100%;
    }

    .experice_idea_title {
        width:  100%;
        padding:  1.347rem 0 1rem;
        text-align:  center;
    }

    .experice_idea_titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    p.experice_idea_titleE {
        width: 100%;
        height: 0.24rem;
        margin-top: 0.107rem;
        font-size: 0.187rem;
        line-height: 0.26rem;
        color: #858585;
    }

    .experice_idea_num_box {
        width:  100%;
        text-align:  center;
    }

    .experice_idea_img {
        overflow:  hidden;
        width: 9.2rem;
        height: 6.12rem;
        margin:  0 auto;
    }

    .experice_idea_img img {
        width:  100%;
        height:  100%;
    }

    .experice_idea_intro {
        width:  100%;
        margin-top: 0.12rem;
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .experice_idea_num {
        display:  flex;
        justify-content:  center;
        align-items:  center;
        padding: 0.92rem 0 1.373rem;
        border-bottom: 0.027rem solid #d5d5d8;
    }

    .experice_idea_num>div {
        flex:  1;
    }

    .experice_idea_num>div p.experice_idea_numbers {
        font-family: Gotham-Bold;
        font-size: 0.8rem;
        font-weight: bold;
        font-stretch: normal;
        line-height: 1.333rem;
        letter-spacing: 0rem;
        color: #22202b;
    }

    .experice_idea_num>div p {
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }



    .experice_idea_desc {
        width: 80%;
        margin:  0 auto;
        padding: 1.307rem 0 1.347rem;
        font-size: 0.32rem;
        text-align:  left;
        line-height: 0.55rem;
        letter-spacing: 0rem;
        color: #858585;
    }
</style>


