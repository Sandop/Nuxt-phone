<template>
    <div id="high_lights_wrap">
        <div class="high_lights_box">
            <div class="high_lights_title_box">
                <div class="high_lights_titleC">
                    <h2>{{highLightsData.highLightsTitleCn1}}</h2>
                    <h2>{{highLightsData.highLightsTitleCn2}}</h2>
                </div>
                <div class="high_lights_titleE">
                    <p>{{highLightsData.highLightsTitleEn}}</p>
                </div>
            </div>
            <div class="high_lights">
                <ul>
                    <li class="high_lights_list" v-for="(list,index) in highLightsData.highLightsList" :key="index">
                        <div class="high_lights_list_top">
                            <div class="high_lights_list_num">{{list.highLightsListNum}}</div>
                            <div class="high_lights_list_title">
                                <p class="high_lights_list_titleC">{{list.highLightsListTitle}}</p>
                                <p class="high_lights_list_titleE">{{list.highLightsListTitleEn}}</p>
                            </div>
                            <div class="high_lights_list_desc">{{list.highLightsListDesc}}</div>
                        </div>
                        <div class="high_lights_list_img">
                            <img :src="list.highLightsListImg" alt="">
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'expericeHighLights',
        props: {
            highLightsData: Object
        }
    }
</script>


<style>
    div#high_lights_wrap {
        width:  100%;
        background-color:  #fff;
    }

    .high_lights_box {
        width:  100%;
        padding: 0 0.373rem 1.333rem;
        box-sizing:  border-box;
        text-align:  center;
    }

    .high_lights_title_box {
        width:  100%;
        padding-top: 1.293rem;
    }

    .high_lights_titleC {
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-size: 0.64rem;
        font-weight: 900;
        line-height: 0.7rem;
        color: #22202b;
    }

    .high_lights_titleE {
        font-size: 0.24rem;
        line-height: 0.5rem;
        color: #858585;
    }

    .high_lights {
        width:  100%;
    }

    .high_lights ul {
        overflow:  hidden;
        width:  100%;
    }

    li.high_lights_list {
        float:  left;
        overflow:  hidden;
        width:  50%;
    }

    .high_lights_list_top {
        overflow:  hidden;
        width:  100%;
        height: 3.6rem;
    }

    .high_lights_list_num {
        margin-top:  0.84rem;
        font-family: Gotham-Medium;
        font-size: 0.8rem;
        font-weight: bold;
        line-height: 0.587rem;
        color: #22202b;
    }

    .high_lights_list_title {
        width:  100%;
    }

    p.high_lights_list_titleC {
        padding-top: 0.2rem;
        font-size: 0.32rem;
        font-weight: 900;
        line-height: 0.307rem;
        color: #22202b;
    }

    p.high_lights_list_titleE {
        padding-top: 0.1rem;
        font-size: 0.187rem;
        line-height: 0.3rem;
        color: #858585;
    }

    .high_lights_list_desc {
        padding-top: 0.18rem;
        font-size: 0.24rem;
        line-height: 0.42rem;
        color: #858585;
    }

    .high_lights_list_img {
        overflow:  hidden;
        width:  100%;
        height: 4.04rem;
    }

    .high_lights_list_img img {
        width: 100%;
    }
</style>

