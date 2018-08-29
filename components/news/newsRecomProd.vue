<template>
    <div id="recom-products">
        <div class="recom-products-box">
            <div class="recom-products-title">
                {{recomProductsTitle}}
            </div>
            <div class="recom-products-list-box">
                <ul>
                    <li class="recom-products-list" v-for="list in recomProductsData" :key="list.proId">
                        <div class="recom-products-list-img">
                            <nuxt-link :to="{name:'products-prodView-id',params:{id: list.proId},query: {typeId: list.proPositionId,classId: list.proTypeId}}"><img :src="list.proImgs[0].proImgSrc" :alt="list.proImgs[0].proImgAlt"></nuxt-link>
                        </div>
                        <div class="recom-products-list-title">
                            <nuxt-link :to="{name: 'products-prodView-id',params:{id: list.proId},query: {typeId: list.proPositionId,classId: list.proTypeId}}">{{list.proName}}</nuxt-link>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'newsRecomProd',
    props: {
        recomProductsTitle: String,
        recomProductsData: Array
    }
}
</script>

<style scoped>
    div#recom-products {
        width: 100%;
    }

    .recom-products-box {
        width: 100%;
    }

    .recom-products-title {
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

    .recom-products-list-box {
        width:  100%;
        padding: 0.733rem 0;
    }

    .recom-products-list-box ul {
        overflow:  hidden;
        width: 100%;
        padding: 0 0.2rem;
        box-sizing:  border-box;
    }

    li.recom-products-list {
        float:  left;
        overflow:  hidden;
        width: 49%;
        margin: 0 0.5%;
        padding-bottom: 0.647rem;
    }

    .recom-products-list-img {
        overflow:  hidden;
        width:  100%;
        height: 3.227rem;
    }

    .recom-products-list-img a {
        display:  block;
        width:  100%;
        height: 100%;
    }

    .recom-products-list-img img {
        width:  100%;
        height: 100%;
    }

    .recom-products-list-title {
        width:  100%;
        height:  0.9rem;
        font-size: 0.32rem;
        line-height: 0.9rem;
        text-align: center;
    }

    .recom-products-list-title a {
        display:  block;
        overflow:  hidden;
        width:  100%;
        height:  100%;
        color:  #999;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }
</style>
