<template>
    <div id="panoramic_hall_wrap">
        <div class="panoramic_hall_box">
            <div class="panoramic_hall_title_box">
                <div class="panoramic_hall_titleC">
                    <h2>{{PanoramicData.PanoramicTitleCn1}}</h2>
                    <h2>{{PanoramicData.PanoramicTitleCn2}}</h2>
                </div>
                <div class="panoramic_hall_titleE">
                    <p>{{PanoramicData.PanoramicTitleEn}}</p>
                </div>
                <div class="panoramic_hall_title_desc">
                    <p>{{PanoramicData.PanoramicTitleDesc}}</p>
                </div>
            </div>
            <div class="panoramic_hall">
                <ul>
                    <li class="panoramic_hall_list" v-for="(list,index) in PanoramicData.PanoramicListData" :key="index">
                        <div class="panoramic_hall_list_img">
                            <img :src="list.PanoramicListImg" alt="">
                        </div>
                        <div class="panoramic_hall_list_intro_box">
                            <div class="panoramic_hall_list_title">
                                <p>{{list.PanoramicListTitle}}</p>
                            </div>
                            <div class="panoramic_hall_list_introC">
                                <p>{{list.PanoramicListIntro}}</p>
                            </div>
                            <div class="panoramic_hall_list_introE">
                                <p>{{list.PanoramicListIntroEn}}</p>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'expericePanoramic',
        props: {
            PanoramicData: Object
        }
    }
</script>

<style scoped>
    div#panoramic_hall_wrap {
        width:  100%;
        background-color: #f9f9fa;
    }

    .panoramic_hall_box {
        width:  100%;
    }

    .panoramic_hall_title_box {
        width:  100%;
        padding: 1.2rem 0 0.893rem;
        text-align:  center;
    }

    .panoramic_hall_titleC {
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-size: 0.64rem;
        font-weight: 900;
        line-height: 0.64rem;
        color: #22202b;
    }

    .panoramic_hall_titleE {
        font-size: 0.24rem;
        line-height: 0.5rem;
        color: #858585;
    }

    .panoramic_hall_title_desc {
        margin-top: 0.733rem;
        font-size: 0.24rem;
        line-height: 0.44rem;
        color: #858585;
    }

    .panoramic_hall {
        width:  100%;
        padding: 0 0.24rem;
        box-sizing:  border-box;
    }

    .panoramic_hall ul {
        overflow:  hidden;
    }

    li.panoramic_hall_list {
        float:  left;
        overflow:  hidden;
        width: 4.4rem;
        margin: 0 0.16rem;
    }

    .panoramic_hall ul li:nth-child(2) {
        float: right;
        margin-top: 6.627rem;
    }

    .panoramic_hall_list_img {
        overflow:  hidden;
        width: 4.4rem;
        height: 8.36rem;
    }

    .panoramic_hall_list_img img {
        width:  100%;
        height:  100%;
    }

    .panoramic_hall_list_intro_box {
        width:  100%;
        padding-bottom: 0.667rem;
    }

    .panoramic_hall_list_title {
        width:  100%;
        padding: 0.827rem 0 0.627rem;
        font-size: 0.36rem;
        font-weight: bold;
        text-align:  left;
        line-height: 0.44rem;
        color: #22202b;
    }

    .panoramic_hall_list_introC {
        font-size: 0.32rem;
        line-height: 0.44rem;
        color: #858585;
    }

    .panoramic_hall_list_introE {
        margin-top:  0.24rem;
        font-size: 0.24rem;
        line-height: 0.317rem;
        color: #cccccc;
    }
</style>


