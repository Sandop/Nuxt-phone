<template>
    <div id="join_requires_wrap">
        <div class="join_requires_box">
            <div class="join_requires">
                <div class="join_requires_title">
                    <div class="join_requires_titleC">
                        <h2>我们的</h2>
                        <h2>合伙要求？</h2>
                    </div>
                    <p class="join_requires_titleE">The partnership requires</p>
                </div>
                <div class="join_requires_cont">
                    <ul>
                        <li class="join_requires_list">
                            <div class="join_requires_list_title">开店面积要求</div>
                            <div class="join_requires_list_intro">
                                <p>实用面积300-800m2</p>
                            </div>
                        </li>
                        <li class="join_requires_list">
                            <div class="join_requires_list_title">开店地标要求</div>
                            <div class="join_requires_list_intro">
                                <p>连锁品牌家居卖场、家具建材临街旺铺、大型商业综合体、高档小区商铺</p>
                            </div>
                        </li>
                        <li class="join_requires_list">
                            <div class="join_requires_list_title">开店经营要求</div>
                            <div class="join_requires_list_intro">
                                <p>做到线上线下价格统一、支付方式统一、服务标准统一、形象统一</p>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>   
            <div class="join_partnership_box">
                <div class="join_partnership_title">
                    <div class="join_partnership_titleC">
                        <h2>合伙流程</h2>
                    </div>
                    <p class="join_partnership_titleE">The partnership process</p>
                </div>
                <div class="join_partnership">
                    <div class="join_partnership_left">
                        <ul>
                            <li class="join_partnership_list">了解品牌</li>
                            <li class="join_partnership_list">立项评测</li>
                            <li class="join_partnership_list">评估报告</li>
                            <li class="join_partnership_list">选址</li>
                            <li class="join_partnership_list">产品选品软装配套</li>
                            <li class="join_partnership_list">公司团队入驻线下体验馆</li>
                            <li class="join_partnership_list">线下体验馆开业</li>
                        </ul>
                    </div>
                    <div class="join_partnership_right">
                        <ul>
                            <li class="join_partnership_list">初步洽谈</li>
                            <li class="join_partnership_list">交品牌保证金</li>
                            <li class="join_partnership_list">签订合作协议</li>
                            <li class="join_partnership_list">线下体验馆装修</li>
                            <li class="join_partnership_list">开业活动策划</li>
                            <li class="join_partnership_list">产品摆场陈列</li>
                            <li class="join_partnership_list">运营团队服务跟进</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'joinRequires'
    }
</script>

<style>
    div#join_requires_wrap {
        width: 100%;
    }

    .join_requires_box {
        width: 100%;
    }

    .join_requires {
        width:  100%;
        padding-bottom: 1.44rem;
    }

    .join_requires_title {
        width:  100%;
        padding: 1.373rem 0 1.187rem;
        text-align:  center;
    }

    .join_requires_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    p.join_requires_titleE {
        margin-top: 0.04rem;
        font-size: 0.187rem;
        line-height: 0.32rem;
        color: #858585;
    }

    .join_requires_cont {
        width:  100%;
        padding: 0 0.773rem 0 0.96rem;
        box-sizing:  border-box;
    }

    .join_requires_cont ul {
        width: 100%;
    }

    li.join_requires_list {
        overflow:  hidden;
        width: 100%;
        padding: 0.467rem 0;
        border-bottom: 0.013rem solid #d5d5d8;
    }

    .join_requires_list_title {
        position:  relative;
        float:  left;
        width: 2.867rem;
        height: 0.84rem;
        background-color: #22202b;
        font-size: 0.32rem;
        text-align:  center;
        line-height: 0.84rem;
        color: #feeabd;
    }

    .join_requires_list_title:after {
        content: '';
        position:  absolute;
        right: 0;
        top: 0;
        border-left: 0.42rem solid #22202b;
        border-top: 0.42rem solid transparent;
        border-right: 0.42rem solid transparent;
        border-bottom: 0.42rem solid transparent;
        transform: translateX(97%);
    }

    .join_requires_list_intro {
        float:  right;
        width: 4.56rem;
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .join_partnership_box {
        width:  100%;
        background-color: #22202b;
        color: #feeabd;
    }

    .join_partnership_title {
        width:  100%;
        padding: 1.373rem 0 0.933rem;
        text-align:  center;
    }

    .join_partnership_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        line-height: 0.64rem;
    }

    p.join_partnership_titleE {
        margin-top: 0.12rem;
        font-size: 0.187rem;
        line-height: 0.34rem;
        color: #feeabd;
    }

    .join_partnership {
        overflow: hidden;
        width:  100%;
        padding-bottom: 1.4rem;
    }

    .join_partnership_left {
        float:  left;
        width:  50%;
        padding-left: 1.067rem;
        box-sizing: border-box;
    }

    .join_partnership_right {
        float:  right;
        width:  50%;
        padding-left:  1.067rem;
        box-sizing:  border-box;
    }

    .join_partnership ul {
        width:  100%;
    }

    li.join_partnership_list {
        padding: 0.433rem 0 0.433rem 0.573rem;
        background: url('~/assets/images/join/join_partnership_list.png') left center no-repeat;
    }

</style>


