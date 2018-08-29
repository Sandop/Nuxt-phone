<template>
    <div id="latest-article">
        <div class="latest-article-box">
            <div class="latest-article-title">
                最新文章
            </div>
            <div class="latest-article-list-box">
                <ul>
                    <li class="latest-article-list" v-for="list in latestArticleData" :key="list.articleId">
                        <div class="latest-article-list-title">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'newsLatestArticle',
        props: {
            latestArticleData: Array
        }
    }
</script>

<style>
    div#latest-article {
        width: 100%;
    }

    .latest-article-box {
        width: 100%;
    }

    .latest-article-title {
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

    .latest-article-list-box {
        width: 100%;
        padding: 0.6rem 0.333rem;
        box-sizing: border-box;
    }

    .latest-article-list-box ul {
        width: 100%;
    }

    li.latest-article-list {
        width: 100%;
        padding: 0.14rem 0;
    }

    .latest-article-list-title {
        position: relative;
        width: 100%;
        padding-left: 0.28rem;
        box-sizing: border-box;
        font-size: 0.32rem;
        line-height: 0.44rem;
    }

    .latest-article-list-title a {
        color: #999;
    }

    .latest-article-list-title:after {
        content: '';
        position: absolute;
        top: 50%;
        left: 0;
        width: 0.067rem;
        height: 0.067rem;
        background-color: #999999;
        border-radius: 50%;
    }
</style>
