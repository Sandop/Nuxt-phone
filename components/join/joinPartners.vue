<template>
    <div id="join_partners_wrap">
        <div class="join_partners_box">
            <div class="join_partners_title">
                <div class="join_partners_titleC">
                    <h2>我们要筑梦</h2>
                    <h2>打造的新星是谁</h2>
                </div>
                <p class="join_partners_titleE">Who are the partners</p>
                <p class="join_partners_title_intro">要求：有经济基础、年轻、实干、符合卫诗理品牌价值观</p>
            </div>
            <div class="join_partners_banner_box">
                <div class="join_partners_banner">
                    <ul>
                        <li class="join_partners_list" v-show="currentNum == 0" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">01</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">客户</p>
                                <p class="join_partners_list_titleE">Customer</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>曾购买、热爱</p>
                                <p>卫诗理家具的</p>
                            </div>
                        </li>
                        <li class="join_partners_list" v-show="currentNum == 1" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">02</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">实体店店主</p>
                                <p class="join_partners_list_titleE">Storekeeper</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>传统家居店</p>
                                <p>急需转型</p>
                                <p>有创新意识的</p>
                            </div>
                        </li>
                        <li class="join_partners_list" v-show="currentNum == 2" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">03</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">设计师&老板</p>
                                <p class="join_partners_list_titleE">Desinger & Boss</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>家装公司</p>
                                <p>设计&软装公司</p>
                                <p>建材行业</p>
                                <p>上下游产业链的</p>
                            </div>
                        </li>
                        <li class="join_partners_list" v-show="currentNum == 3" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">04</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">社会精英</p>
                                <p class="join_partners_list_titleE">Customer</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>拥有海量客户资源</p>
                                <p>正寻找家装</p>
                                <p>产业链机会的</p>
                            </div>
                        </li>
                        <li class="join_partners_list" v-show="currentNum == 4" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">05</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">勇闯家</p>
                                <p class="join_partners_list_titleE">Entrepreneurs</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>正在寻找</p>
                                <p>市场商机</p>
                                <p>想创业的</p>
                            </div>
                        </li>
                        <li class="join_partners_list" v-show="currentNum == 5" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">06</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">异业合作伙伴</p>
                                <p class="join_partners_list_titleE">Investors</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>从事各美业</p>
                                <p>寻找跨界</p>
                                <p>投资方向的</p>
                            </div>
                        </li>
                        <li class="join_partners_list" v-show="currentNum == 6" @mouseenter="stop" @mouseleave="go">
                            <div class="join_partners_list_num">07</div>
                            <div class="join_partners_list_title">
                                <p class="join_partners_list_titleC">梦想家</p>
                                <p class="join_partners_list_titleE">Dreamer</p>
                            </div>
                            <div class="join_partners_list_line"></div>
                            <div class="join_partners_list_intro">
                                <p>有共同</p>
                                <p>事业理想的</p>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'joinPartners',
        data (){
            return {
                currentNum: 0,
                timer: '' 
            }
        },
        created (){
            //在dom加载完成后下个tick中开始轮播
            this.$nextTick(()=>{
                this.timer = setInterval(() => {
                    this.autoPlay()
                },3000)
            });
        },
        methods: {
            autoPlay (){
                let length = 7;
                this.currentNum ++;
                if (this.currentNum > length-1) {
                    this.currentNum = 0;
                }
            },
            go (){
                this.timer = setInterval(() => {this.autoPlay()},3000)
            },
            stop (){
                clearInterval (this.timer);
                this.timer = null;
            }
        }
    }
</script>

<style scoped>
    div#join_partners_wrap {
        width:  100%;
    }

    .join_partners_title {
        width:  100%;
        padding: 1.28rem 0 1.453rem;
        text-align: center;
    }

    .join_partners_box {
        width:  100%;
        padding-bottom: 1.67rem;
    }

    .join_partners_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    p.join_partners_titleE {
        font-size: 0.32rem;
        line-height: 0.44rem;
        color: #858585;
    }

    p.join_partners_title_intro {
        padding-top:  0.24rem;
        font-size: 0.32rem;
        line-height: 0.36rem;
        color: #858585;
    }

    .join_partners_banner_box {
        position:  relative;
        width:  100%;
    }

    .join_partners_banner {
        overflow:  hidden;
        width: 6.227rem;
        height: 7.96rem;
        margin:  0 auto;
    }

    li.join_partners_list {
        display: inline-block;
        width: 6.227rem;
        height: 7.96rem;
        border: solid 0.053rem #22202b;
        box-sizing:  border-box;
        text-align:  center;
    }

    .join_partners_list_num {
        padding-top: 0.733rem;
        font-family: Gotham-Black;
        font-size: 1.6rem;
        font-weight: 900;
        line-height: 1.8rem;
        color: #22202b;
    }

    .join_partners_list_title {
        padding-top:  0.587rem;
        font-size: 0.587rem;
        line-height: 0.6rem;
        color: #22202b;
    }

    p.join_partners_list_titleE {
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .join_partners_list_line {
        margin: 0.8rem auto 0.9rem;
        width: 1.453rem;
        height: 0.037rem;
        background-color: #d5d5d8;
    }

    .join_partners_list_intro {
        font-size: 0.373rem;
        line-height: 0.44rem;
        color: #858585;
    }

    span.join_partners_banner_pre {
        position:  absolute;
        top: 50%;
        left: 5%;
        width: 0.427rem;
        height: 0.493rem;
        transform: translateY(-50%);
        background: #ccc;
    }

    span.join_partners_banner_next {
        position: absolute;
        top: 50%;
        right: 5%;
        width: 0.427rem;
        height: 0.493rem;
        transform: translateY(-50%);
        background: #ccc;
    }
</style>


