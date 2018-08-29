<template>
    <div id="love-products">
        <div class="love-products-box">
            <div class="love-products-title">
                猜你喜欢
            </div>
            <div class="love-products-list-box">
                <ul>
                    <li class="love-products-list" v-for="(list,index) in loveArticleData" :key="list.articleId" v-if="index<2">
                        <div class="love-products-list-img">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">
                                <img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt">
                            </nuxt-link>
                        </div>
                        <div class="love-products-list-title">
                            <nuxt-link  :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'newsLove',
        props: {
            loveArticleData: Array
        }
    }
</script>

<style>
    div#love-products {
        width: 100%;
    }

    .love-products-box {
        width: 100%;
    }

    .love-products-title {
        width: 100%;
        height: 1.84rem;
        padding-left: 0.347rem;
        border-bottom: 0.027rem solid rgba(46, 44, 58, .2);
        box-sizing: border-box;
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.373rem;
        font-weight: bold;
        line-height: 2.9rem;
        color: #000000;
    }

    .love-products-list-box {
        width: 100%;
        padding: 0.6rem 0.333rem;
        box-sizing: border-box;
    }

    .love-products-list-box ul {
        overflow: hidden;
        width: 100%;
        padding: 0 0.2rem;
        box-sizing: border-box;
    }

    li.love-products-list {
        float: left;
        overflow: hidden;
        width: 49%;
        margin: 0 0.5%;
        padding-bottom: 0.647rem;
    }

    .love-products-list-img {
        overflow: hidden;
        width: 100%;
        height: 3.227rem;
    }

    .love-products-list-img a {
        display: block;
        width: 100%;
        height: 100%;
    }

    .love-products-list-img img {
        width:  100%;
        height: 100%;
    }

    .love-products-list-title {
        width: 100%;
        height: 0.9rem;
        font-size: 0.32rem;
        line-height: 0.9rem;
        text-align: center;
    }

    .love-products-list-title a {
        display: block;
        overflow: hidden;
        width: 100%;
        height: 100%;
        color: #999;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
</style>
