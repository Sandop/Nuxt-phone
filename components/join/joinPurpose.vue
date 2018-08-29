<template>
    <div id="join_purpose_wrap">
        <div class="join_purpose_box">
            <div class="join_purpose_title_box">
                <div class="join_purpose_title">
                    <div class="join_purpose_titleC">
                        <h2>我们的目的</h2>
                        <h2>是什么？</h2>
                    </div>
                    <p class="join_purpose_titleE">What is our purpose</p>
                </div>
            </div>
            <div class="join_purpose_plan">
                <p class="join_purpose_plan_word">筑</p>
                <p class="join_purpose_plan_num">18</p>
                <p class="join_purpose_plan_word">座梦想之城</p>
            </div>
            <div class="join_purpose_plan">
                <p class="join_purpose_plan_word">打造</p>
                <p class="join_purpose_plan_num">365</p>
                <p class="join_purpose_plan_word">个创业新星</p>
            </div>
            <div class="join_purpose_intro">
                <p>推进产业发展，实现品牌使命</p>
            </div>
            <div class="join_purpose_introE">
                <p>Build 18 dream cities and create 365 new stars.</p>
                <p>Promote industrial development and realize the brand mission.</p>
            </div>
            <div class="join_purpose_bg"><img src="~/assets/images/join/join_purpose_bg.png"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'joinPurpose'
    }
</script>

<style scoped>
    div#join_purpose_wrap {
        width:  100%;
        background-color: #f9f9fa;
    }

    .join_purpose_box {
        width:  100%;
        padding-bottom: 1.28rem;
        text-align:  center;
    }

    .join_purpose_title_box {
        width: 100%;
        padding: 1.387rem 0 1rem;
    }

    .join_purpose_title {
        width:  100%;
    }

    .join_purpose_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    p.join_purpose_titleE {
        margin-top: 0.147rem;
        font-size: 0.187rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .join_purpose_plan {
        width: 100%;
        padding-bottom: 1.187rem;
    }

    p.join_purpose_plan_word {
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    p.join_purpose_plan_num {
        font-size: 0.827rem;
        font-weight: bold;
        line-height: 1.2rem;
        color: #22202b;
    }

    .join_purpose_intro {
        padding: 0 1.4rem;
        box-sizing: border-box;
        font-size: 0.32rem;
        line-height: 0.44rem;
        letter-spacing: 0rem;
        color: #858585;
    }

    .join_purpose_introE {
        padding-bottom: 1.013rem;
        font-size: 0.16rem;
        line-height: 0.271rem;
        color: #d6d6d6;
    }

    .join_purpose_bg {
        overflow:  hidden;
        width: 100%;
        height:  2.27rem;
    }

    .join_purpose_bg img {
        width:  100%;
        height:  100%;
    }
</style>


