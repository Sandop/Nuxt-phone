<template>
    <div class="products-details">
        <div class="products-details-box clearfix">
            <div class="prod-details-warp">
                <div class="prod-details-title">
                    <p>商品详情</p>
                </div>
                <div class="prod-details" v-html="prodViewData.proMsg">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'prodDetails',
        props: {
            prodViewData: Object
        }
    }
</script>

<style>
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

    .products-details {
        width: 100%;
    }

    .products-details-box {
        width: 100%;
        padding: 2rem 0;
    }

    .prod-details-warp {
        width: 100%;
        padding:  0 0.32rem;
        box-sizing:  border-box;
    }

    .prod-details-title {
        width:  100%;
        font-size: 0.48rem;
        text-align: center;
        line-height: 1rem;
        color: #22202b;
    }

    .prod-details-title p {
        position:  relative;
        display: inline-block;
    }

    .prod-details-title p:after {
        content:  '';
        position: absolute;
        bottom:  0;
        left: 50%;
        width: 0.827rem;
        height: 0.027rem;
        transform: translateX(-50%);
        background-color: #d4c2a1;
    }

    .prod-details {
        width:  100%;
        padding-top: 0.587rem;
    }

    .prod-details p {
        width: 100%;
    }

    .prod-details img {
        width: 100%;
        height: 100%;
    }
</style>
