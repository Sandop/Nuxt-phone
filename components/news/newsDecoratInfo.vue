<template>
    <div id="decoration-placement">
        <div class="decoration-place-box">
            <div class="decoration-place-top">
                <div class="decoration-place-titleC">
                    <h2>装修摆放</h2>
                </div>
                <div class="decoration-place-titleE">
                    <p>Decoration Placement</p>
                </div>
            </div>
            <div class="decoration-place-content">
                <ul>
                    <li class="decoration-place-list clearfix" v-for="list in decorationInfo" :key="list.articleId">
                        <div class="decoration-place-img">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">
                                <img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt">
                            </nuxt-link>
                        </div>
                        <div class="decoration-place-title">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
                        </div>
                        <div class="decoration-place-time"><p>{{getTime(list.articleAddTime)}}</p></div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'newsDecoratInfo',
    props: {
        decorationInfo: Array
    },
    methods: {
        getTime(time){
            var time = time.slice(5, 10);
            return time;
        }
    }
}
</script>

<style scoped>
    div#decoration-placement {
        width:  100%;
    }

    .decoration-place-box {
        width: 100%;
        padding: 0 0.32rem;
        box-sizing: border-box;
    }

    .decoration-place-top {
        width: 100%;
        padding: 1.24rem 0 0.813rem;
        text-align: center;
    }

    .decoration-place-titleC {
        height: 0.64rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    .decoration-place-titleE {
        font-size: 2.992px;
        font-size: 0.187rem;
        line-height: 0.34rem;
        color: #858585;
    }

    .decoration-place-content {
        width: 100%;
    }

    .decoration-place-content ul {
        width: 100%;
    }

    li.decoration-place-list {
        width: 100%;
    }

    .decoration-place-img {
        display:  none;
        overflow:  hidden;
        width: 9.227rem;
        height: 6.4rem;
        margin:  0 auto;
    }

    .decoration-place-img a {
        display:  block;
        width:  100%;
        height: 100%;
    }

    .decoration-place-img img {
        width:  100%;
        height: 100%;
    }

    .decoration-place-content {
        width: 100%;
    }

    .decoration-place-content ul {
        width: 100%;
    }

    li.decoration-place-list {
        width: 100%;
    }

    .decoration-place-img {
        display:  none;
        overflow:  hidden;
        width: 9.227rem;
        height: 6.4rem;
        margin:  0 auto;
    }

    .decoration-place-img a {
        display:  block;
        width:  100%;
        height: 100%;
    }

    .decoration-place-img img {
        width:  100%;
        height: 100%;
    }

    .decoration-place-title {
        position:  relative;
        float:  left;
        max-width: 85%;
        height: 0.66rem;
        padding-left: 0.15rem;
        box-sizing:  border-box;
    }

    .decoration-place-time {
        float:  right;
        font-size: 0.32rem;
        line-height: 0.66rem;
        color: #858585;
    }

    .decoration-place-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        font-size: 0.32rem;
        line-height: 0.66rem;
        color: #666;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }

    .decoration-place-title:after {
        content:  '';
        position:  absolute;
        top: 50%;
        left: 0;
        width:  0.04rem;
        height:  0.04rem;
        background:  #858585;
        border-radius: 50%;
    }

    .decoration-place-content ul li:nth-child(4n) {
        padding-bottom: 1.347rem;    
    }

    .decoration-place-content ul li:nth-child(4n+1) .decoration-place-img {
        display:block;     
    }

    .decoration-place-content ul li:nth-child(4n+1) .decoration-place-time {
        display:none;     
    }

    .decoration-place-content ul li:nth-child(4n+1) .decoration-place-title {
        width: 100%;
        max-width: 100%;
        padding: 0.12rem 0;
        box-sizing: content-box;    
    }

    .decoration-place-content ul li:nth-child(4n+1) .decoration-place-title::after {
        display: none;
    }

    .decoration-place-content ul li:nth-child(4n+1) .decoration-place-title a {
        color: #22202b;    
    }
</style>
