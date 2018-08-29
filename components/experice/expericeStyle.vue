<template>
    <div id="native_level_wrap">
        <div class="native_level_box">
            <div class="native_level_title_box clearfix">
                <div class="native_level_title_left">
                    <div class="native_level_titleC">
                        <h2>{{styleData.styleTitle}}</h2>
                    </div>
                    <div class="native_level_title_desc">
                        <p v-for="(list,index) in styleData.styleDesc" :key="index">{{list}}</p>
                    </div>
                </div>
            </div>
            <div class="native_level_show">
                <ul>
                    <li class="native_level_list" v-for="(list,index) in styleData.styleImg" :key="index">
                        <img :src="list" alt="">
                    </li>
                </ul>
            </div>
            <div class="chinese_style_more" v-if="styleData.styleMore">
                <p>更多系列，到店尊享</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'expericeStyle',
        props: {
            styleData: Object
        }
    }
</script>

<style>
    div#native_level_wrap {
        width:  100%;
    }

    .native_level_box {
        width:  100%;
        text-align:  center;
    }

    .native_level_title_box {
        width:  100%;
        padding: 1.36rem 0 0.586rem;
    }

    .native_level_titleC {
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-size: 0.64rem;
        font-weight: 900;
        line-height: 0.7rem;
        color: #22202b;
    }

    .native_level_title_desc {
        margin-top:  0.2rem;
        font-size: 0.24rem;
        font-weight: normal;
        font-stretch: normal;
        line-height: 0.42rem;
        letter-spacing: 0rem;
        color: #858585;
    }

    .native_level_show {
        width:  100%;
        padding:  0 0.4rem 0 0.387rem;
        box-sizing:  border-box;
    }

    .native_level_show ul{
        width: 100%;
    }

    li.native_level_list {
        overflow:  hidden;
        width:  100%;
        margin-top: 0.24rem;
    }

    li.native_level_list img {
        width: 100%;
    }

    .chinese_style_more {
        width:  100%;
        padding: 0.813rem 0 1.293rem;
        font-size: 0.32rem;
        font-weight: 900;
        line-height: 0.4rem;
        color: #22202b;
    }
</style>


