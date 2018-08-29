<template>
    <div id="recom-infomation">
        <div class="recom-info-box">
            <div class="recom-info-top">
                <div class="recom-info-titleC">
                    <h2>推荐资讯</h2>
                </div>
                <div class="recom-info-titleE">
                    <p>Recommendation information</p>
                </div>
            </div>
            <div class="recom-info-content clearfix">
                <ul>
                    <li class="recom-info-list" v-for="(list,index) in recomInfo" :key="list.articleId" v-if="index<3">
                        <div class="recom-info-img">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">
                                <img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt">
                            </nuxt-link>
                        </div>
                        <div class="recom-info-title-box">
                            <div class="recom-info-title">
                                <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
                            </div>
                        </div>
                        <div class="recom-info-deesc" >{{getTxt(list.articleText,index,136,42)}}</div>
                        <div class="recom-info-more">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">了解更多</nuxt-link>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'newsRecomInfo',
    props: {
        recomInfo: Array
    },
    methods: {
        getTxt (str,index,num1=136,num2=42){
            var txt = str.replace(/<\/?.+?>/g,"").replace(/&nbsp;/ig,"").replace(/(^\s+)|(\s+$)/g,"").replace(/\s/g,''); 
            if (index == 0) {
                //截取指定字数末尾显示省略号
                txt = txt.length < num1 ? txt : txt.substring(0,num1).concat('...');
            } else {
                txt = txt.length < num2 ? txt : txt.substring(0,num2).concat('...');
            }
            return txt;
        }
    }
}
</script>
<style scoped>
    div#recom-infomation {
        width:  100%;
    }

    .recom-info-box {
        width:  100%;
        padding:  0 0.333rem;
        box-sizing:  border-box;
    }

    .recom-info-top {
        width:  100%;
        padding: 1.253rem 0 0.867rem;
        text-align:  center;
    }

    .recom-info-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .recom-info-titleE {
        margin-top:  0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    .recom-info-content {
        width: 100%;
    }

    .recom-info-content ul {
        overflow:  hidden;
        width: 100%;
    }

    li.recom-info-list {
        float:  left;
        width:  50%;
        padding-bottom: 1.2rem;
    }

    .recom-info-content ul li.recom-info-list:first-child {
        width: 100%;
    }

    .recom-info-content ul li.recom-info-list:first-child .recom-info-img {
        display:  none;
    }

    .recom-info-img {
        overflow:  hidden;
        width: 4.52rem;
        height: 3.133rem;
        margin:  0 auto;
    }

    .recom-info-img a {
        display:  block;
        width:  100%;
        height: 100%;
    }

    .recom-info-img a img {
        width:  100%;
        height: 100%;
    }

    .recom-info-title-box {
        width: 100%;
        height:  1rem;
    }

    .recom-info-title {
        width:  100%;
        height: 100%;
    }

    .recom-info-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        font-size: 0.32rem;
        text-align:  left;
        line-height: 1rem;
        color: #22202b;
        white-space:  nowrap;
        text-overflow:  ellipsis;
    }

    .recom-info-deesc {
        width:  100%;
        font-size: 0.24rem;
        line-height: 0.44rem;
        color: #858585;
    }

    .recom-info-more {
        width: 2.6rem;
        height: 0.8rem;
        margin: 0.5rem auto 0;
        border: solid 0.04rem #000000;
    }

    .recom-info-more a {
        display:  block;
        width:  100%;
        height: 100%;
        font-size: 0.32rem;
        text-align:  center;
        line-height: 0.8rem;
        color: #000000;
    }

    .recom-info-content ul li.recom-info-list:first-child .recom-info-title a {
        font-weight: bold;
        text-align: center;
    }

    .recom-info-content ul li.recom-info-list:first-child .recom-info-more {
        display:  none;
    }
</style>


