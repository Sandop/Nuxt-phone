<template>
    <div id="place_desc_wrap">
        <div class="place_desc_box clearfix">
            <div class="place_desc_left">
                <div class="place_title_box">
                    <p class="place_titleC">{{placeDescData.placeDescTitle}}</p>
                    <p class="place_titleE">{{placeDescData.placeDescTitleE}}</p>
                </div>
                <div class="place_desc">
                    <p class="place_descC">{{placeDescData.placeDesc}}</p>
                </div>
                <div class="place_desc_right">
                    <ul>
                        <li class="place_desc_img" v-for="(item,index) in placeDescData.placeDescImgSrc" :key="index" v-show="currentNum == index" @mouseenter="stop" @mouseleave="go" >
                            <img :src="item" alt="">
                        </li>
                    </ul>
                </div>
                <div class="place_tag_box">
                    <ul>
                        <li class="place_tag_list" v-for="(item,index) in placeDescData.placeDescImgName" :key="index" :class="{active: index == currentNum}" @click="tabIndex(index)" @mouseenter="stop" @mouseleave="go">{{item}}</li>
                    </ul>
                </div>
            </div>
            
        </div>
    </div>
</template>

<script>
    export default {
        name: 'expericePlaceDesc',
        props: {
            placeDescData: Object
        },
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
            tabIndex (index){
                this.currentNum =index;
            },
            autoPlay (){
                let length = this.placeDescData.placeDescImgName.length;
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
    div#place_desc_wrap {
        width:  100%;
    }

    .place_desc_box {
        width:  100%;
    }

    .place_desc_left {
        width:  100%;
        padding: 1.36rem 0.813rem 1.293rem 0.68rem;
        box-sizing:  border-box;
        text-align:  center;
    }

    .place_title_box {
        width:  100%;
    }

    p.place_titleC {
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        font-size: 0.64rem;
        line-height: 0.64rem;
        color: #22202b;
    }

    p.place_titleE {
        font-size: 0.187rem;
        line-height: 0.58rem;
        color: #858585;
    }

    .place_desc {
        padding: 0.547rem 0 1.067rem;
        font-size: 0.32rem;
        font-weight: normal;
        font-stretch: normal;
        line-height: 0.48rem;
        letter-spacing: 0rem;
        color: #858585;
    }

    .place_desc_right {
        overflow:  hidden;
        width: 6.933rem;
        height: 8rem;
        margin:  0 auto;
    }

    .place_desc_right ul {
        width:  100%;
        height:  100%;
    }

    li.place_desc_img {
        width:  100%;
        height:  100%;
    }

    li.place_desc_img img {
        width:  100%;
        height:  100%;
    }

    .place_tag_box {
        width:  100%;
        padding-top: 0.773rem;
        text-align:  center;
    }

    li.place_tag_list {
        display:  none;
        width: 2.107rem;
        height: 0.747rem;
        border: solid 0.04rem #000000;
        font-size: 0.259rem;
        line-height: 0.747rem;
        color: #858585;
    }

    li.place_tag_list.active {
        display:  inline-block;
        color: #feeabd;
        background: #000;
    }
</style>


