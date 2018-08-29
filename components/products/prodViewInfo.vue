<template>
    <div class="products-msg">
        <div class="products-msg-box">
            <div class="products-pic-wrap">
                <ProdViewImages :bigImage="prodViewData.proImgs" :middleImage="prodViewData.proImgs" :smallImage="prodViewData.proImgs"></ProdViewImages>
            </div>
            <div class="products-wrod-wrap">
                <div class="products-view-title">
                    <p>{{prodViewData.proName}}</p>
                </div>
                <div class="products-price">
                    <div class="products-price-word">价格：</div>
                    <div class="products-price-box">
                        <span class="products-price-mark">￥</span>
                        <span class="products-price-num">{{prodViewData.proPrice}}</span>
                    </div>
                </div>
                <div class="products-parameter">
                    <div class="products-parameter-word">产品参数：</div>
                    <div class="products-par-details-box">
                        <p v-for="(value,key,index) in prodViewData.param" :key="index">{{key}}：{{value}}</p>
                    </div>
                </div>
                <div class="prod-buy-now">
                    <a :href="`${prodViewData.proSrc}`" target="_blank" rel="nofollow">立即购买</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import ProdViewImages from '~/components/products/ProdViewImages'

    export default {
        name: 'prodViewInfo',
        props: {
            prodViewData: Object
        },
        components: {
			ProdViewImages
		}
    }
</script>

<style>
    .products-msg {
        width: 100%;
    }

    .products-msg-box {
        width: 100%;
    }

    .products-pic-wrap {
        width: 100%;
    }

    .products-wrod-wrap {
        width:  100%;
        padding: 0 0.4rem;
        box-sizing:  border-box;
    }

    .products-view-title {
        width:  100%;
        height:  1.6rem;
        font-size: 0.4rem;
        font-weight: bold;
        line-height: 1.6rem;
        color: #22202b;
    }

    .products-view-title p {
        overflow:  hidden;
        width: 100%;
        height:  100%;
        text-overflow:  ellipsis;
        white-space:  nowrap;
    }

    .products-price {
        overflow:  hidden;
        width: 100%;
        height:  1rem;
    }

    .products-price-word {
        float:  left;
        height: 100%;
        font-size: 0.373rem;
        font-weight:  bold;
        line-height: 1rem;
        color: #858585;
    }

    .products-price-box {
        float: left;
        height: 100%;
        font-family: SourceHanSerifCN-Bold;
        color: #22202b;
    }

    span.products-price-mark {
        font-size: 0.283rem;
        line-height: 0.24rem;
    }

    span.products-price-num {
        font-size: 0.485rem;
        font-weight: bold;
        line-height: 1rem;
    }

    .products-parameter {
        width: 100%;
        border-bottom: 0.013rem solid #dcdcdc;
    }

    .products-parameter-word {
        width:  100%;
        height: 1rem;
        font-size: 0.373rem;
        font-weight: bold;
        line-height: 1rem;
        color: #858585;
        border-bottom: 0.013rem solid #dcdcdc;
    }

    .products-par-details-box {
        width: 100%;
        padding: 0.3rem 0;
    }

    .products-par-details-box p {
        display:  inline-block;
        width:  50%;
        height:  0.64rem;
        font-size: 0.32rem;
        line-height: 0.64rem;
        color: #858585;
    }

    .prod-buy-now {
        width:  100%;
        padding-top:  0.56rem;
        text-align:  center;
    }

    .prod-buy-now a {
        display: inline-block;
        width: 7.547rem;
        height: 0.947rem;
        background-color: #22202b;
        font-size: 0.373rem;
        line-height: 0.947rem;
        color: #ffe9c0;
    }
</style>
