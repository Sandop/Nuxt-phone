<template>
    <div id="news-view">
        <div class="news-view-box">
            <div class="news-view-details-wrap">
                <div class="news-view-title-box">
                    <div class="news-view-title"><h1>{{articleData.articleName}}</h1></div>
                    <div class="news-view-info">
                        <div class="news-view-sort">
                            <span class="news-view-info-title">分类:</span>
                            <span class="news-view-sort-cont">{{articleData.articleCategory.articleCategoryName}}</span>
                        </div>
                        <div class="news-view-access">
                            <span class="news-view-info-title">访问:</span>
                            <span class="news-view-access-cont">{{articleData.pageViews.pageViewsCount}}</span>
                        </div>
                         <div class="news-view-edit">
                            <span class="news-view-info-title">编辑:</span>
                            <span class="news-view-edit-cont">{{articleData.articleEditor.articleEditorName}}</span>
                        </div>
                        <div class="news-view-time">
                            <span class="news-view-info-title">发布:</span>
                            <span class="news-view-time-cont">{{getTime(articleData.articleAddTime)}}</span>
                        </div>
                    </div>
                </div>
                <div class="news-view-details" v-html="articleData.articleText">
                </div>
            </div>
            <div class="news-view-other" v-if="preNextData.length == 1 && !isQuestions">
                <div class="news-view-prev" v-if="preNextData[0].articleId < this.$route.params.id">
                    <nuxt-link :to="{name:'news-newsView-id',params:{id:preNextData[0].articleId},query: {category:preNextData[0].articleCategoryId}}">
                        <span>上一篇:</span>
                        <span class="news-view-prev-title">{{preNextData[0].articleName}}</span>
                    </nuxt-link>
                </div>
                <div class="news-view-next" v-if=" preNextData[0].articleId > this.$route.params.id">
                    <nuxt-link :to="{name:'news-newsView-id',params:{id:preNextData[0].articleId},query: {category:preNextData[0].articleCategoryId}}">
                        <span>下一篇:</span>
                        <span class="news-view-next-title">{{preNextData[0].articleName}}</span>
                    </nuxt-link>
                </div>
            </div>
            <div class="news-view-other" v-if="preNextData.length == 2  && !isQuestions">
                <div class="news-view-prev">
                    <nuxt-link :to="{name:'news-newsView-id',params:{id:preNextData[0].articleId},query: {category:preNextData[0].articleCategoryId}}">
                        <span>上一篇:</span>
                        <span class="news-view-prev-title">{{preNextData[0].articleName}}</span>
                    </nuxt-link>
                </div>
                <div class="news-view-next">
                    <nuxt-link :to="{name:'news-newsView-id',params:{id:preNextData[1].articleId},query: {category:preNextData[1].articleCategoryId}}">
                        <span>下一篇:</span>
                        <span class="news-view-next-title">{{preNextData[1].articleName}}</span>
                    </nuxt-link>
                </div>
            </div>
            <div class="news-view-other" v-if="preNextData.length == 1 && isQuestions">
					<div class="news-view-prev" v-if="preNextData[0].articleId < this.$route.params.id">
						<nuxt-link :to="{name:'service-id',params:{id:preNextData[0].articleId}}">
							<span>上一篇:</span>
							<span class="news-view-prev-title">{{preNextData[0].articleName}}</span>
						</nuxt-link>
					</div>
					<div class="news-view-next" v-if=" preNextData[0].articleId > this.$route.params.id">
						<nuxt-link :to="{name:'service-id',params:{id:preNextData[0].articleId}}">
							<span>下一篇:</span>
							<span class="news-view-next-title">{{preNextData[0].articleName}}</span>
						</nuxt-link>
					</div>
				</div>
				<div class="news-view-other" v-if="preNextData.length == 2 && isQuestions">
					<div class="news-view-prev">
						<nuxt-link :to="{name:'service-id',params:{id:preNextData[0].articleId}}">
							<span>上一篇:</span>
							<span class="news-view-prev-title">{{preNextData[0].articleName}}</span>
						</nuxt-link>
					</div>
					<div class="news-view-next">
						<nuxt-link :to="{name:'service-id',params:{id:preNextData[1].articleId}}">
							<span>下一篇:</span>
							<span class="news-view-next-title">{{preNextData[1].articleName}}</span>
						</nuxt-link>
					</div>
				</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'newsView',
        props: {
            articleData: Object,
            preNextData: Array,
            isQuestions: {
                typeof: Boolean,
                default: false
            }
        },
        methods: {
            getTime(time){
                var time = time.slice(0, 10);
                return time;
            }
        }
    }
</script>

<style>
    div#news-view {
        width:  100%;
    }

    .news-view-box {
        width:  100%;
        padding-top: 1.333rem;
    }

    .news-view-details-wrap {
        width: 100%;
        padding-bottom: 1.3rem;
    }

    .news-view-title-box {
        width:  100%;
        padding: 0.5rem 0;
        border-top: 0.027rem solid rgba(46, 44, 58, 0.2);
        border-bottom: 0.027rem solid rgba(46, 44, 58, 0.2);
    }

    .news-view-title {
        width:  100%;
        padding:  0 0.56rem;
        box-sizing:  border-box;
        font-size: 0.4rem;
        font-weight: bold;
        line-height: 0.6rem;
        text-align: center;
        color: #22202b;
    }

    .news-view-title h1 {
        font-weight: bold;
    }

    .news-view-info {
        display:  flex;
        padding: 0.373rem 0.56rem 0;
        justify-content:  space-between;
        align-items:  center;
        flex-wrap:  wrap;
        box-sizing:  border-box;
        font-size: 0.32rem;
        text-align:  left;
        line-height: 0.48rem;
        color: #858585;
    }

    .news-view-info>div {
        width: 50%;
    }

    .news-view-access {
        text-align:  right;
    }

    .news-view-time {
        text-align:  right;
    }

    .news-view-details {
        width:  100%;
        padding: 0.9rem 0.64rem 0;
        box-sizing:  border-box;
        font-size: 0.32rem;
        line-height: 0.48rem;
        color: #858585;
    }

    .news-view-details img {
        width: 100%;
        height: 100%;
    }

    .news-view-details p {
        width: 100%;
    }

    .news-view-other {
        width:  100%;
        padding: 0 0.65rem;
        box-sizing:  border-box;
    }

    .news-view-other>div {
        width: 100%;
        height: 0.54rem;
        font-size: 0.36rem;
        line-height: 0.54rem;
        letter-spacing: 0rem;
    }

    .news-view-other>div a {
        display:  block;
        overflow: hidden;
        width:  100%;
        height:  100%;
        color: #22202b;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }
</style>
