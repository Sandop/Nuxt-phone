<template>
    <div id="bread-nav">
        <div class="brand-nav-box clearfix">
            <div class="brand-nav-content">
                <div class="brand-nav-title"><span>当前位置:</span></div>
                <div class="brand-nav-list">
                    <ul>
                        <li><nuxt-link to="/">首页</nuxt-link></li>
                        <li>></li>
                        <li><nuxt-link to="/service/contact">服务中心</nuxt-link></li>
                        <li>></li>
                        <li><nuxt-link to="/service/contact">联系我们</nuxt-link></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'contactBrandNav'
    }
</script>

<style scoped>
    div#bread-nav {
        width:  100%;
        height:  auto;
    }

    .brand-nav-box {
        width:  1200px;
        margin:  0 auto;
        color:  #858585;
        font-size: 14px;
        text-align:  left;
        line-height: 70px;
    }

    .brand-nav-content{
        float: left;
    }
    .brand-nav-title {
        float:  left;
    }

    .brand-nav-list {
        float:  left;
        overflow:  hidden;
    }

    .brand-nav-list ul {
        overflow: hidden;
    }

    .brand-nav-list ul li {
        float:  left;
        padding: 0 5px;
    }

    .brand-nav-list ul li a {
        display:  block;
        width:  100%;
        height:  100%;
        color: #858585;
    }

    .brand-nav-list ul li:last-child a {
        color: #22202b;
    }

    .brand-nav-list ul li a:hover {
        color: #22202b;
    }

    div#bread-nav .brand-nav-box {
        line-height:  150px;
    }
</style>


