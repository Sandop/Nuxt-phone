<template>
    <div id="partner_contact_wrap">
        <div class="partner_contact_box">
            <div class="join_contact_title">
                <div class="join_contact_titleC">
                    <h2>合伙联系人</h2>
                </div>
                <p class="join_contact_titleE">Partnership contact</p>
            </div>
            <div class="join_contact_box">
                <div class="join_contact_left">
                    <ul>
                        <li class="join_contact_intro">联系人:大卫 David</li>
                        <li class="join_contact_intro">联系方式:173 0263 3888</li>
                        <li class="join_contact_intro">总部地址:深圳市宝安区固戍泰华梧桐岛11栋5-9层</li>
                        <li class="join_contact_intro">体验馆地址：东莞市厚街镇家具大道209号</li>
                    </ul>
                </div>
                <div class="join_contact_address">
                    <p>一厂地址:东莞市厚街镇双岗家具大道伟业路13号</p>
                    <p>二厂地址：东莞市厚街镇白濠工业区</p>
                    <p>三厂地址：东莞市厚街镇环冈第二工业区</p>
                </div>
                <div class="join_contact_right">
                    <div class="join_contact_code">
                        <div class="join_contact_code_img">
                            <img src="~/assets/images/join/join_contact_code_img.png">
                        </div>
                        <div class="join_contact_code_txt">
                            <p>扫一扫了解更多</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'joinPartnerContact'
    }
</script>

<style>
    div#partner_contact_wrap {
        width: 100%;
    }

    .partner_contact_box {
        width: 100%;
    }

    .join_contact_title {
        width: 100%;
        padding:  1.347rem 0 0.827rem;
        text-align:  center;
    }

    .join_contact_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    p.join_contact_titleE {
        margin-top: 0.12rem;
        font-size: 0.187rem;
        line-height: 0.304rem;
        color: #858585;
    }

    .join_contact_box {
        width:  100%;
        padding: 0 1.293rem 0 1.307rem;
        box-sizing:  border-box;
    }

    .join_contact_left {
        width:  100%;
    }

    .join_contact_left ul {
        width:  100%;
    }

    li.join_contact_intro {
        width:  100%;
        padding-top: 0.28rem;
        border-bottom: 0.013rem solid #e5e5e5;
        font-size: 0.32rem;
        text-align:  left;
        line-height: 0.624rem;
        color: #55545f;
    }

    .join_contact_address {
        width:  100%;
        padding: 0.547rem 0 0.8rem;
    }

    .join_contact_address p {
        font-size: 0.32rem;
        line-height: 0.64rem;
        color: #55545f;
    }

    .join_contact_right {
        display:  flex;
        width: 100%;
        padding-bottom: 1.307rem;
        justify-content:  center;
        align-items:  center;
    }

    .join_contact_code_img {
        overflow:  hidden;
        width: 2.987rem;
        height: 2.96rem;
    }

    .join_contact_code_img img {
        width: 100%;
    }

    .join_contact_code_txt {
        font-size: 0.32rem;
        line-height: 0.4rem;
        text-align:  center;
        color: #55545f;
    }
</style>


