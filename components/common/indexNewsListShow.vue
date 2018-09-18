<template>
	<div class="news-tab-box">
	  <div class="news-first-box">
	    <div class="news-first">
	        <div class="news-first-left">
	            <img :src="indexFirstNewsList.articleImg.articleImgSrc" :alt="indexFirstNewsList.articleImg.articleImgAlt">
	        </div>
	        <div class="news-first-right">
                <div class="news-first-title">
                    <nuxt-link :to="{name:'news-newsView-id',params:{id:indexFirstNewsList.articleId},query: {category: indexFirstNewsList.articleCategoryId}}"><b>{{indexFirstNewsList.articleName}}</b></nuxt-link>
                </div>
	            <div class="news-first-intro">{{getTxt(indexFirstNewsList.articleText,46)}}</div>
                <div class="news-first-times">
                    <p>{{getTime(indexFirstNewsList.articleAddTime,0,10)}}</p>
                </div>
	        </div>
	    </div>
	  </div>
	  <div class="news-list">
	    <ul>
            <li v-for="(item,index) in indexNewsList" :key="index" v-if="index<6">
                <div class="news-list-title">
                    <nuxt-link :to="{name:'news-newsView-id',params:{id:item.articleId},query: {category: item.articleCategoryId}}"><b>{{item.articleName}}</b></nuxt-link>
                </div>
                <div class="news-list-times">
                    <p>{{getTime(item.articleAddTime)}}</p>
                </div>
            </li>
	    </ul>
	  </div>
	</div>
</template>

<script>
	export default {
		name: 'indexNewsListShow',
		props: {
			indexFirstNewsList: Object,
			indexNewsList: Array
		},
		methods: {
            getTxt (str,num = 150){
                var txt = str.replace(/<\/?.+?>/g,"").replace(/(^\s+)|(\s+$)/g,"").replace(/\s/g,''); 
                txt = txt.length < num ? txt : txt.substring(0,num).concat('...');
                return txt;
            },
            getTime(time,num1=5,num2=10){
                var time = time.slice(num1, num2);
                return time;
            }
        }
	}
</script>

<style scoped>
	.news-tab-box {
        width:  100%;
    }

    .news-first-box {
        overflow: hidden;
        width:  100%;
        padding-bottom: 0.533rem;
        border-bottom: 0.013rem solid #d5d5d8;
    }

    .news-first {
        width:  100%;
        padding:  0 0.4rem;
        box-sizing:  border-box;
    }

    .news-first-left {
        position:  relative;
        float:  left;
        overflow:  hidden;
        width: 3.507rem;
        height: 2.56rem;
    }

    .news-first-left img {
        width: 100%;
        height: 100%;
    }

    .news-first-right {
        float:  right;
        overflow:  hidden;
        width: 5.387rem;
    }

    .news-first-title {
        width:  100%;
        height: 0.547rem;
    }

    .news-first-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        font-family: MicrosoftYaHei-Bold;
        font-size: 0.373rem;
        font-weight:  bold;
        color: #22202b;
        line-height:  0.547rem;
        white-space:  nowrap;
        text-overflow:  ellipsis;
    }

    .news-tab-box b {
        overflow: hidden;
        display: block;
        width: 100%;
        height: 100%;
        font-weight: normal;
        text-overflow: ellipsis;
        white-space: nowrap;
    }

    .news-first-intro {
        overflow:  hidden;
        width: 100%;
        font-size: 0.293rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .news-first-times {
        overflow:  hidden;
        width:  100%;
        margin-top: 0.4rem;
        font-size: 0.206rem;
        line-height: 0.265rem;
        text-align:  right;
        color: #858585;
    }

    .news-list {
        width:  100%;
        padding: 0.68rem 0.413rem 0 0.493rem;
        box-sizing:  border-box;
    }

    .news-list ul {
        width:  100%;
    }

    .news-list ul li {
        overflow:  hidden;
        width:  100%;
        height:  0.613rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        line-height: 0.613rem;
        color: #999999;
        white-space: nowrap;
        text-overflow: ellipsis;
    }

    .news-list-title {
        position:  relative;
        float:  left;
        width: 80%;
        height: 100%;
        padding-left: 2%;
        box-sizing:  border-box;
    }

    .news-list-times {
        float:  right;
        width: 15%;
        text-align:  right;
    }

    .news-list-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        line-height: 0.613rem;
        color: #999999;
        white-space:  nowrap;
        text-overflow:  ellipsis;
    }

    .news-list-title:after {
        content:  '';
        position:  absolute;
        top: 50%;
        left:  0;
        width:  0.027rem;
        height:  0.027rem;
        background:  #999;
        border-radius:  50%;
    }
</style>