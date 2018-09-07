<template>
    <div id="company-industry-information">
        <div class="company-industry-info-box">
            <div class="company-info-box">
                <div class="company-info-top">
                    <div class="company-info-titleC">
                        <h2>公司资讯</h2>
                    </div>
                    <div class="company-info-titleE">
                        <p>Company information</p>
                    </div>
                </div>
                <div class="company-info-content">
                    <ul>
                        <li class="company-info-list" v-for="(list,index) in companyInfo" :key="list.articleId">
                            <div class="company-info-title">
                                <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}"><h2>{{list.articleName}}</h2></nuxt-link>
                            </div>
                            <div class="company-info-desc">{{getTxt(list.articleText,index,90)}}</div>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="industry-info-box">
                <div class="industry-info-top">
                    <div class="industry-info-titleC">
                        <h2>行业资讯</h2>
                    </div>
                    <div class="industry-info-titleE">
                        <p>Industry information</p>
                    </div>
                </div>
                <div class="industry-info-content">
                    <ul>
                        <li class="industry-info-list" v-for="(list,index) in industryInfo" :key="list.articleId">
                            <div class="industry-info-title">
                                <nuxt-link :to="{name: 'news-newsView-id',params:{id:list.articleId},query: {category: list.articleCategoryId}}"><h2>{{list.articleName}}</h2></nuxt-link>
                            </div>
                            <div class="industry-info-desc">{{getTxt(list.articleText,index,90)}}</div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'newsComIndusInfo',
        props: {
            companyInfo: Array,
            industryInfo: Array
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
    div#company-industry-information {
        width:  100%;
        background-color: #f9f9fa;
        padding-bottom: 1.32rem;
    }

    .company-industry-info-box {
        width: 100%;
        padding:  0 0.347rem;
        box-sizing:  border-box;
    }

    .company-info-box {
        width: 100%;
    }

    .company-info-top {
        width:  100%;
        padding: 1.347rem 0 0.6653rem;
        text-align:  center;
    }

    .company-info-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .company-info-titleE {
        font-size: 0.187rem;
        line-height: 0.34rem;
        color: #858585;
    }

    .company-info-content {
        width: 100%;
    }

    .company-info-content ul {
        width: 100%;
    }

    li.company-info-list {
        width:  100%;
    }

    .company-info-title {
        width:  100%;
        height: 0.48rem;
        font-size: 0.32rem;
        line-height: 0.48rem;
        color: #22202b;
    }

    .company-info-desc {
        display:  none;
        width: 100%;
        padding-top:  0.36rem;
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .company-info-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        color: #22202b;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }

    .company-info-content ul li:first-child {
        padding-bottom: 0.707rem;
    }

    .company-info-content ul li:first-child .company-info-title a h2{
        font-family: MicrosoftYaHei-Bold;
        font-weight: bold;
    }

    .company-info-content ul li:first-child .company-info-desc {
        display:  block;
    }
    .industry-info-box {
        width: 100%;
    }

    .industry-info-top {
        width:  100%;
        padding: 1.347rem 0 0.6653rem;
        text-align:  center;
    }

    .industry-info-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .industry-info-titleE {
        font-size: 0.187rem;
        line-height: 0.34rem;
        color: #858585;
    }

    .industry-info-content {
        width: 100%;
    }

    .industry-info-content ul {
        width: 100%;
    }

    li.industry-info-list {
        width:  100%;
    }

    .industry-info-title {
        width:  100%;
        height: 0.48rem;
        font-size: 0.32rem;
        line-height: 0.48rem;
        color: #22202b;
    }

    .industry-info-desc {
        display:  none;
        width: 100%;
        padding-top:  0.36rem;
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .industry-info-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        color: #22202b;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }

    .industry-info-content ul li:first-child {
        padding-bottom: 0.707rem;
    }

    .industry-info-content ul li:first-child .industry-info-title a h2{
        font-family: MicrosoftYaHei-Bold;
        font-weight: bold;
    }

    .industry-info-content ul li:first-child .industry-info-desc {
        display:  block;
    }
</style>


