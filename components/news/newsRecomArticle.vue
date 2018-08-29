<template>
    <div id="recom-article">
        <div class="recom-article-box">
            <div class="recom-article-title">
               推荐文章
            </div>
            <div class="recom-article-list-box">
                <div class="recom-article-left">
                    <ul>
                        <li class="recom-article-list" v-for="list in recomArticleData" :key="list.articleId">
                            <div class="recom-article-list-title">
                                <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
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
        name: 'newsRecomArticle',
        props: {
            recomArticleData: Array
        }
    }
</script>

<style scoped>
    div#recom-article {
        width:  100%;
    }

    .recom-article-box {
        width: 100%;
    }

    .recom-article-title {
        width: 100%;
        height: 1.84rem;
        padding-left: 0.347rem;
        border-bottom: 0.027rem solid rgba(46, 44, 58, 0.2);
        box-sizing:  border-box;
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.373rem;
        font-weight: bold;
        line-height: 2.9rem;
        color: #000000;
    }

    .recom-article-list-box {
        width: 100%;
        padding: 0.6rem 0.333rem;
        box-sizing: border-box;
    }   

    .recom-article-left {
        width:  100%;
    }

    .recom-article-left ul {
        width: 100%;
    }

    li.recom-article-list {
        width:  100%;
        padding: 0.14rem 0;
    }

    .recom-article-list-title {
        position:  relative;
        width:  100%;
        padding-left:  0.28rem;
        box-sizing:  border-box;
        font-size: 0.32rem;
        line-height: 0.44rem;
    }

    .recom-article-list-title a {
        color: #999;
    }

    .recom-article-list-title:after {
        content:  '';
        position:  absolute;
        top: 50%;
        left: 0;
        width: 0.067rem;
        height: 0.067rem;
        background-color: #999999;
        border-radius: 50%;
    }
</style>
