<template>
  <section class="container">
      <!-- banner -->
      <VBanner :bannerData="bannerData"></VBanner>
      <!-- 品牌故事 -->
      <indexStory></indexStory>
      <!-- 体验馆 -->
      <indexExperience></indexExperience>
      <!-- 产品介绍 -->
      <div id="index-products">
        <div class="products-content">
          <div class="products-content-top">
            <div class="products-content-top-titleC">
              <h2>产品介绍</h2>
            </div>
            <div class="products-content-top-titleE">Products Introduce</div>
            <div class="products-content-top-description">品质生活，爱家有道</div>
          </div>
          <div class="products-content-box">
            <div class="products-kind-container">
              <ul class="products-kind-nav">
                <li class="products-kind" v-for="(item,index) in indexProdNav" :key="item.proCategoryId" :class="{active:index == clickProdIndex}" @click="getProdList(index)">{{getTxt(item.proCategoryName)}}</li>
              </ul>
              <div class="products-tab-content">
                <prodListShow :prodList="indexProdList6" :showNewMore="true" :typeId="97" v-show="0 == clickProdIndex"></prodListShow>
                <prodListShow :prodList="indexProdList5" :showMore="false" :typeId="96" v-show="1 == clickProdIndex"></prodListShow>
                <prodListShow :prodList="indexProdList1" :showMore="true" :typeId="1" v-show="2 == clickProdIndex"></prodListShow>
                <prodListShow :prodList="indexProdList2" :showMore="true" :typeId="2" v-show="3 == clickProdIndex"></prodListShow>
                <prodListShow :prodList="indexProdList3" :showMore="true" :typeId="3" v-show="4 == clickProdIndex"></prodListShow>
                <prodListShow :prodList="indexProdList4" :showMore="true" :typeId="4" v-show="5 == clickProdIndex"></prodListShow>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- 新闻资讯部分 -->
      <div id="index-news">
        <div class="news-content">
          <div class="news-content-top">
            <div class="news-content-top-titleC"><h2>新闻资讯</h2></div>
            <div class="news-content-top-titleE">News Center</div>
            <div class="news-content-top-description">一切资讯都是有价值的</div>
          </div>
          <div class="news-content-box">
            <div class="news-kind-container">
              <ul class="news-kind-nav">
                <li class="news-kind" v-for="(item,index) in $store.state.headNewsNav" :key="index" :class="{active:index == clickNewsIndex}" @click="getNewsList(index)">{{item.articleCategoryName}}</li>
              </ul>
              <div class="news-tab-content">
                <indexNewsListShow :indexFirstNewsList="indexFirstNewsList1" :indexNewsList="indexNewsList1" v-show="0 == clickNewsIndex"></indexNewsListShow>
                <indexNewsListShow :indexFirstNewsList="indexFirstNewsList2" :indexNewsList="indexNewsList2" v-show="1 == clickNewsIndex"></indexNewsListShow>
                <indexNewsListShow :indexFirstNewsList="indexFirstNewsList3" :indexNewsList="indexNewsList3" v-show="2 == clickNewsIndex"></indexNewsListShow>
                <indexNewsListShow :indexFirstNewsList="indexFirstNewsList4" :indexNewsList="indexNewsList4" v-show="3 == clickNewsIndex"></indexNewsListShow>
                <indexNewsListShow :indexFirstNewsList="indexFirstNewsList5" :indexNewsList="indexNewsList5" v-show="4 == clickNewsIndex"></indexNewsListShow>
              </div>
            </div>
          </div>
        </div>
      </div>  
  </section>
</template>
<script>
  import axios from 'axios'
  import AppLogo from '~/components/AppLogo.vue'
  import VHeader from '~/components/home/header'
  import VFooter from '~/components/home/footer'
  import VBanner from '~/components/home/banner'
  import indexStory from '~/components/home/indexStory'
  import indexExperience from '~/components/home/indexExperience'
  import prodListShow from '~/components/common/prodListShow'
  import indexNewsListShow from '~/components/common/indexNewsListShow'

  export default {
    data(){
      return {
        clickProdIndex:0,
        clickNewsIndex: 0
      }
    },
    components: {
      AppLogo,
      VHeader,
      VFooter,
      VBanner,
      indexStory,
      indexExperience,
      prodListShow,
      indexNewsListShow
    },
    head () {
      return {
        title:this.metaData.navigationTitle,
        meta: [
          {name:'keywords',hid: 'keywords',content:`${this.metaData.navigationKeyword}`},
          {name:'description',hid:'description',content:`${this.metaData.navigationDescription}`}
        ]
      }
    },
    async asyncData({params,store}){
      //首页head信息
      let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/1`);
      //banner数据动态获取
      let banner = await axios(`${store.state.wordpressAPI}/banner/selectAllByTpye/1`);
      //首页新闻信息
      let indexFirstNewsList1 = await axios(`${store.state.wordpressAPI}/article/getRecommend/1`);
			let indexFirstNewsList2 = await axios(`${store.state.wordpressAPI}/article/getRecommend/2`);
			let indexFirstNewsList3 = await axios(`${store.state.wordpressAPI}/article/getRecommend/3`);
			let indexFirstNewsList4 = await axios(`${store.state.wordpressAPI}/article/getRecommend/4`);
			let indexFirstNewsList5 = await axios(`${store.state.wordpressAPI}/article/getRecommend/5`);

			let indexNewsList1 = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/1/9`);
			let indexNewsList2 = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/2/9`);
			let indexNewsList3 = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/3/9`);
			let indexNewsList4 = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/4/9`);
      let indexNewsList5 = await axios(`${store.state.wordpressAPI}/article/getRecommendsByCategoryId/5/9`);
      
      //首页产品展示信息
      let indexProdNav = await axios(`${store.state.wordpressAPI}/proCategory/showFirst`);

			let indexProdList1 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/1`);
			let indexProdList2 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/2`);
			let indexProdList3 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/3`);
      let indexProdList4 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/4`);
      let indexProdList5 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/96`);
      let indexProdList6 = await axios(`${store.state.wordpressAPI}/product/selectByPosition/97`);
      
      return {
        metaData: metaData.data,
        bannerData: banner.data,
        //首页新闻信息
        indexFirstNewsList1: indexFirstNewsList1.data,
        indexFirstNewsList2: indexFirstNewsList2.data,
        indexFirstNewsList3: indexFirstNewsList3.data,
        indexFirstNewsList4: indexFirstNewsList4.data,
        indexFirstNewsList5: indexFirstNewsList5.data,
        indexNewsList1: indexNewsList1.data,
        indexNewsList2: indexNewsList2.data,
        indexNewsList3: indexNewsList3.data,
        indexNewsList4: indexNewsList4.data,
        indexNewsList5: indexNewsList5.data,
        //首页产品信息
        indexProdNav: indexProdNav.data,
        indexProdList1: indexProdList1.data,
        indexProdList2: indexProdList2.data,
        indexProdList3: indexProdList3.data,
        indexProdList4: indexProdList4.data,
        indexProdList5: indexProdList5.data,
        indexProdList6: indexProdList6.data,
      } 
    },
    methods: {
      getProdList (index){
        this.clickProdIndex = index;
      },
      getTxt (str){
          var txt = str.replace(/<\/?.+?>/g,"").replace(/(^\s+)|(\s+$)/g,"").replace(/\s/g,''); 
          txt = txt.length < 2 ? txt : txt.substring(0,2);
          return txt;
      },
      getNewsList (index){
        this.clickNewsIndex = index;
      }

    }
  }
</script>

<style scoped>
  .container {
    width: 100%;
    height: auto;
  }

  .title {
    font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
  }
  /*products*/
    div#index-products {
        width:  100%;
    }

    .products-content {
        width:  100%;
        padding-bottom: 1.36rem;
    }

    .products-content-top {
        width: 100%;
        text-align: center;
        padding-top: 1.373rem;
        padding-bottom: 0.947rem;
    }

    .products-content-top-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .products-content-top-titleE {
        width: 100%;
        height: 0.24rem;
        margin-top: 0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    .products-content-top-description {
        height: 0.32rem;
        margin-top: 0.12rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        font-weight: normal;
        line-height: 0.32rem;
        color: #858585;
    }

    .products-content-box {
        width:  100%;
    }

    .products-kind-container {
        width: 100%;
    }

    ul.products-kind-nav {
        display:  flex;
        justify-content:  center;
        align-items:  center;
    }

    li.products-kind {
        height:  0.907rem;
        margin: 0 0.4rem;
        color: #979797;
        font-size: 0.373rem;
        border-bottom: 0.053rem solid transparent;
    }

    li.products-kind.active {
        color: #000;
        border-bottom: 0.053rem solid #000;
    }

    .products-tab-content {
      width: 100%;
    }
  /*products*/
  /*news*/
    div#index-news {
        width:  100%;
        background-color: #f5f5f5;
    }

    .news-content {
        width:  100%;
    }

    .news-content-top {
        width: 100%;
        text-align: center;
        padding-top: 1.373rem;
        padding-bottom: 0.947rem;
    }

    .news-content-top-titleC {
        height: 0.613rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.613rem;
    }

    .news-content-top-titleE {
        width: 100%;
        height: 0.24rem;
        margin-top: 0.107rem;
        font-size: 0.187rem;
        line-height: 0.24rem;
        color: #858585;
    }

    .news-content-top-description {
        height: 0.32rem;
        margin-top: 0.12rem;
        font-family: MicrosoftYaHei;
        font-size: 0.32rem;
        font-weight: normal;
        line-height: 0.32rem;
        color: #858585;
    }

    .news-kind-container {
        width: 100%;
    }

    ul.news-kind-nav {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap:  wrap;
    }

    li.news-kind {
        height: 0.907rem;
        margin: 0 0.4rem;
        color: #979797;
        font-size: 0.373rem;
        border-bottom: 0.053rem solid transparent;
    }

    li.news-kind.active {
        color: #000;
        border-bottom: 0.053rem solid #000;
    }

    .news-tab-content {
        width:  100%;
        padding-top: 1.347rem;
        padding-bottom: 1.387rem;
    }
  /*news*/
</style>
