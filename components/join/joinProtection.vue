<template>
    <div id="join_protection_wrap">
        <div class="join_protection_box">
            <div class="join_protection_title_box">
                <div class="join_protection_title">
                    <div class="join_protection_titleC">
                        <h2>我们的核心利益</h2>
                        <h2>保障是什么？</h2>
                    </div>
                    <p class="join_protection_titleE">What is the guarantee of our core interests</p>
                </div>
                <div class="join_protection_img"><img src="~/assets/images/join/join_protection_img.png"></div>
            </div>
            <div class="join_partners_intro">
                <p>承诺投资0亏损，限前<span>30</span>名城市合伙人</p>
                <p>投资资金按周期返还，最快保证<span>10</span>个月回本</p>
            </div>
            <div class="join_partners_introE">
                <p>Promise to invest 0 loss, limited to 30 city partners:</p>
                <p>The investment funds are returned by cycle, and the maximum guarantee is 10 months.</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'joinProtection'
    }
</script>

<style scoped>
    div#join_protection_wrap {
        width:  100%;
    }

    .join_protection_box {
        width: 100%;
    }

    .join_protection_title_box {
        width:  100%;
        padding: 1.36rem 0 0.48rem;
        text-align:  center;
    }

    .join_protection_title {
        padding-bottom: 1.093rem;
    }

    .join_protection_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    p.join_protection_titleE {
        font-size: 0.187rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .join_protection_img {
        width: 5.453rem;
        height: 1.56rem;
        margin:  0 auto;
    }

    .join_protection_img img {
        width:  100%;
        height: 100%;
    }

    .join_partners_intro {
        font-size: 0.349rem;
        text-align:  center;
        line-height: 0.44rem;
        color: #858585;
    }

    .join_partners_intro span {
        font-family: Gotham-Bold;
        font-size: 0.931rem;
        font-weight: bold;
        color: #22202b;
    }

    .join_partners_intro p {
        padding-top: 0.707rem;
    }

    .join_partners_introE {
        width:  100%;
        padding:  0.613rem 0 1.4rem;
        font-size: 0.16rem;
        line-height: 0.271rem;
        text-align:  center;
        color: #d6d6d6;
    }
</style>


