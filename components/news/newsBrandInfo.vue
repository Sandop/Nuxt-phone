<template>
    <div id="brand-selection">
        <div class="brand-selection-box">
            <div class="brand-selection-top">
                <div class="brand-selection-titleC">
                    <h2>品牌选购</h2>
                </div>
                <div class="brand-selection-titleE">
                    <p>Brand Selection</p>
                </div>
            </div>
            <div class="brand-selection-content">
                <ul>
                    <li class="brand-selection-list" v-for="(list,index) in brandInfo" :key="list.articleId" v-if="index < 4">
                        <div class="brand-selection-list-img">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">
                                <img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt">
                            </nuxt-link>
                        </div>
                        <div class="brand-selection-list-title">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}"><h2>{{list.articleName}}</h2></nuxt-link>
                        </div>
                        <div class="brand-selection-list-desc">{{getTxt(list.articleText,index,115,32)}}</div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'newsBrandInfo',
        props: {
            brandInfo: Array
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
    div#brand-selection {
        width: 100%;
    }

    .brand-selection-box {
        width: 100%;
        padding: 0 0.333rem;
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
    }

    .brand-selection-top {
        width: 100%;
        padding: 1.24rem 0 0.813rem;
        text-align: center;
    }

    .brand-selection-titleC {
        height: 0.64rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    .brand-selection-titleE {
        font-size: 0.187rem;
        line-height: 0.34rem;
        color: #858585;
    }

    .brand-selection-content {
        width: 100%;
    }

    .brand-selection-content ul {
        width: 100%;
    }

    li.brand-selection-list {
        width: 100%;
    }

    .brand-selection-content ul li:first-child .brand-selection-list-img {
        display: block;
    }

    .brand-selection-list-img {
        display: none;
        overflow: hidden;
        width: 9.32rem;
        height: 5.173rem;
        margin: 0 auto;
    }

    .brand-selection-list-img a {
        display: block;
        width: 100%;
        height: 100%;
    }

    .brand-selection-list-img img {
        width:  100%;
        height: 100%;
    }

    .brand-selection-list-title {
        width: 100%;
        height: 1.467rem;
    }

    .brand-selection-list-title a {
        display: block;
        overflow: hidden;
        width: 100%;
        height: 100%;
        font-size: 0.32rem;
        line-height: 1.467rem;
        color: #22202b;
        text-overflow: ellipsis;
        white-space: nowrap;
    }

    .brand-selection-list-title a h2{
        display: block;
        overflow: hidden;
        width: 100%;
        height: 100%;
        text-overflow: ellipsis;
        white-space: nowrap;
    }

    .brand-selection-list-desc {
        width: 100%;
        padding-bottom: 0.5rem;
        font-size: 0.32rem;
        line-height: 0.44rem;
        color: #858585;
    }
</style>
