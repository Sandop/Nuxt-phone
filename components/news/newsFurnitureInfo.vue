<template>
    <div id="furniture-encyclopedia">
        <div class="furniture-encyclopedia-box">
            <div class="furniture-encyclopedia-top">
                <div class="furniture-encyclopedia-titleC">
                    <h2>家具百科</h2>
                </div>
                <div class="furniture-encyclopedia-titleE">
                    <p>Furniture Encyclopedia</p>
                </div>
            </div>
            <div class="furniture-encyclopedia-content clearfix">
                <ul>
                    <li class="furniture-encyclopedia-list" v-for="(list,index) in furnitureInfo" :key="list.articleId" v-if="index < 4">
                        <div class="fur-ency-list-img">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">
                                <img :src="list.articleImg.articleImgSrc" :alt="list.articleImg.articleImgAlt">
                            </nuxt-link>
                        </div>
                        <div class="fur-ency-list-title">
                            <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}">{{list.articleName}}</nuxt-link>
                        </div>
                        <div class="fur-ency-list-desc">{{getTxt(list.articleText,index,115,32)}}</div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'newsFurnitureInfo',
        props: {
            furnitureInfo: Array
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

<style>
    div#furniture-encyclopedia {
        width: 100%;
    }

    .furniture-encyclopedia-box {
        width: 100%;
        padding:  0 0.333rem;
        box-sizing:  border-box;
    }

    .furniture-encyclopedia-top {
        width:  100%;
        padding:  1.24rem 0 0.813rem;
        text-align:  center;
    }

    .furniture-encyclopedia-titleC {
        height: 0.64rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    .furniture-encyclopedia-titleE {
        font-size: 0.187rem;
        line-height: 0.34rem;
        color: #858585;
    }

    .furniture-encyclopedia-content {
        width: 100%;
    }

    .furniture-encyclopedia-content ul {
        width: 100%;
    }

    li.furniture-encyclopedia-list {
        width:  100%;
    }

    .furniture-encyclopedia-content ul li:first-child .fur-ency-list-img {
        display: block;
    }

    .fur-ency-list-img {
        display:  none;
        overflow:  hidden;
        width: 9.32rem;
        height: 5.173rem;
        margin:  0 auto;
    }

    .fur-ency-list-img a {
        display:  block;
        width:  100%;
        height: 100%;
    }

    .fur-ency-list-img img {
        width:  100%;
        height: 100%;
    }

    .fur-ency-list-title {
        width: 100%;
        height: 1.467rem;
    }

    .fur-ency-list-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        font-size: 0.32rem;
        line-height: 1.467rem;
        color: #22202b;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }

    .fur-ency-list-desc {
        width: 100%;
        padding-bottom: 0.5rem;
        font-size: 0.32rem;
        line-height: 0.44rem;
        color: #858585;
    }
</style>
