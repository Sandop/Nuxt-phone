<template>
    <div id="common-banner">
        <div class="common-banner-container">
            <div class="common-banner-img">
                <img src="~/assets/images/brand/brand_banner.jpg">
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'brandBanner'
    }
</script>
<style scoped>
    div#common-banner {
        width:  100%;
        height: 6.667rem;
    }

    .common-banner-container {
        width:  100%;
        height:  100%;
    }

    .common-banner-img {
        position:  relative;
        overflow:  hidden;
        width:  100%;
        height: 100%;
    }

    .common-banner-img img {
        position: absolute;
        top: 50%;
        left: 50%;
        overflow: hidden;
        transform: translate(-61%,-50%) scale(0.45);
    }
</style>


