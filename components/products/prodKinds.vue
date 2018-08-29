<template>
    <div class="products-kinds" :class="{background_color: prodKindsData.showBgColor}">
        <div class="products-kinds-box">
            <div class="products-kinds-top">
                <div class="products-kinds-title">
                    <div class="products-kinds-titleC"><h2>{{prodKindsData.prodKindsTitleC}}</h2></div>
                    <div class="products-kinds-titleE">{{prodKindsData.prodKindsTitleE}}</div>
                </div>
                <div class="products-kinds-link" v-if="! (prodKindsData.typeId == 97)">
                    <ul>
                        <li class="products-kinds-link-list" v-for="(list,index) in $store.state.headProdNav[(prodKindsData.typeId - 1)].children" :key="index">
                            <nuxt-link :to="{name: 'products-typeId',params: {typeId: prodKindsData.typeId},query: {classId: list.proCategoryId}}">{{list.proCategoryName}}</nuxt-link>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="living-room-content products-kinds-content">
                <prodListShow :prodList="prodList" :showMore="prodKindsData.showMore" :showNewMore="prodKindsData.showNewMore" :showBgColor="prodKindsData.showBgColor"  :typeId="prodKindsData.typeId"></prodListShow>
            </div>
        </div>
    </div>
</template>

<script>
  	import prodListShow from '~/components/common/prodListShow'

    export default {
        name: 'prodKinds',
        props: {
            prodKindsData: Object,
            prodList: Array
        },
        components: {
            prodListShow
        }
    }
</script>

<style>
    .products-kinds {
        width: 100%;
    }

    .background_color {
        background-color: #f5f5f5;
    }

    .products-kinds-box {
        width: 100%;
        padding-bottom: 1.373rem;
    }

    .products-kinds-top {
        width:  100%;
        text-align:  center;
    }

    .products-kinds-title {
        width:  100%;
        padding: 1.373rem 0 0.8rem;
    }

    .products-kinds-titleC {
        height: 0.64rem;
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    .products-kinds-titleE {
        margin-top:  0.133rem;
        font-family: GothamRounded-Book;
        font-size: 0.213rem;
        line-height: 0.44rem;
        color: #858585;
    }

    .products-kinds-link {
        width: 94%;
        margin: 0 auto;
        padding-bottom: 0.773rem;
    }

    .products-kinds-link ul {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
    }

    li.products-kinds-link-list {
        display:  inline-block;
        height: 1rem;
        padding:  0 0.3rem;
        font-size: 0.373rem;
        line-height: 1rem;
    }

    li.products-kinds-link-list a {
        display:  block;
        width:  100%;
        height:  100%;
        color: #979797;
        border-bottom: 0.04rem solid transparent;
    }

    li.products-kinds-link-list a:hover {
        color: #000;
        border-bottom: 0.04rem solid #000;
    }
</style>
