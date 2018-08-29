<template>
    <div id="common-banner">
        <div class="common-banner-container">
            <div class="common-banner-img">
                <img :src="bannerSrc">
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'commonBanner',
        props: {
            bannerSrc: {
                type: String,
                default: 'http://img.visney.cn/img/nuxtPhone/experice/banner.png'
            }
        }
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
        overflow:  hidden;
        width:  100%;
        height: 100%;
    }

    .common-banner-img img {
        width: 100%;
        height: 100%;
    }
</style>


