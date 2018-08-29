<template>
    <div id="experice_service">
        <div class="experice_service_box">
            <div class="experice_service_title">
                <div class="experice_service_titleC"><h2>服务体系</h2></div>
                <p class="experice_service_titleE">For what service</p>
                <p class="experice_service_title_desc">以美为本，创造体验式营销新高度</p>
            </div>
            <div class="experice_service_list_box">
                <div class="experice_service_left">
                    <ul>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img1.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">酒店</p>
                                <p class="experice_service_list_titleE">Hotel</p>
                                <p class="experice_service_list_desc">禅意升腾·四季如春</p>
                            </div>
                        </li>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img4.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">红酒</p>
                                <p class="experice_service_list_titleE">Red wine</p>
                                <p class="experice_service_list_desc">法国勃艮第·醇香第一味</p>
                            </div>
                        </li>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img2.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">时装</p>
                                <p class="experice_service_list_titleE">Latest fashion</p>
                                <p class="experice_service_list_desc">不脱装·要时尚</p>
                            </div>
                        </li>
                    </ul>
                </div>
                <div class="experice_service_right">
                    <ul>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img3.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">花艺</p>
                                <p class="experice_service_list_titleE">Flower art</p>
                                <p class="experice_service_list_desc">花花世界 罗曼蒂克</p>
                            </div>
                        </li>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img6.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">咖啡</p>
                                <p class="experice_service_list_titleE">Coffee</p>
                                <p class="experice_service_list_desc">诗意生活·一杯一念一世界</p>
                            </div>
                        </li>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img7.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">艺术展</p>
                                <p class="experice_service_list_titleE">Art Exhibition</p>
                                <p class="experice_service_list_desc">简生活·酷创作</p>
                            </div>
                        </li>
                        <li class="experice_service_list">
                            <div class="experice_service_list_img"><img src="~/assets/images/experice/experice_service_list_img5.png"></div>
                            <div class="experice_service_list_title">
                                <p class="experice_service_list_titleC">摄影</p>
                                <p class="experice_service_list_titleE">Photography</p>
                                <p class="experice_service_list_desc">无限回忆·定格美好</p>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'experienceServer'
    }
</script>

<style>
    div#experice_service {
        width:  100%;
    }

    .experice_service_box {
        width: 100%;
    }

    .experice_service_title {
        width: 100%;
        padding: 1.32rem 0 0.88rem;
        text-align: center;
    }

    .experice_service_titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    p.experice_service_titleE {
        width: 100%;
        height: 0.24rem;
        margin-top: 0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    p.experice_service_title_desc {
        height: 0.32rem;
        margin-top: 0.12rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        font-weight: normal;
        line-height: 0.32rem;
        color: #858585;
    }

    .experice_service_list_box {
        overflow: hidden;
    }



    li.experice_service_list {width: 4.48rem;margin:  0 auto;}

    .experice_service_left {
        float: left;
        width: 50%;
        padding-top: 2.6rem;
    }

    .experice_service_right {
        float: right;
        width: 50%;
    }

    .experice_service_list_img {
        overflow:  hidden;
        width:  100%;
    }

    .experice_service_list_img img {
        width:  100%;
    }

    .experice_service_list_title {
        width:  100%;
        padding: 0.653rem 0 2.027rem;
        text-align:  center;
    }

    p.experice_service_list_titleC {
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.373rem;
        font-weight: bold;
        line-height: 0.4rem;
        color: #22202f;
    }

    p.experice_service_list_titleE {
        font-size: 0.24rem;
        line-height: 0.4rem;
        color: #858585;
    }

    p.experice_service_list_desc {
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }
</style>


