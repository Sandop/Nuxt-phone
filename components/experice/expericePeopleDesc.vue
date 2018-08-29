<template>
    <div id="place_people_desc_wrap">
        <div class="place_people_desc_box clearfix">
            <div class="place_people_desc_right">
                <div class="place_people_desc_right_title">
                    <p class="place_people_desc_right_titleE">{{peopleDescData.peopleDescTitleCn}}</p>
                    <p class="place_people_desc_right_titleC">{{peopleDescData.peopleDescTitleEn}}</p>
                </div>
                <div class="place_people_desc_right_img">
                    <img :src="peopleDescData.placeImgSrc" alt="">
                </div>
            </div>
            <div class="place_people_desc_left">
                <div class="place_people_desc_left_img">
                    <img  :src="peopleDescData.peopleImgSrc" alt="">
                </div>
                <div class="place_people_name_left">
                    <div class="place_people_name"><p>{{peopleDescData.peopleName}}</p></div>
                    <div class="place_people_desc">
                        <div class="place_people_descC">
                            <p>{{peopleDescData.peopleDescCn}}</p>
                        </div>
                        <div class="place_people_descE">
                            <p>{{peopleDescData.peopleDescEn}}</p> 
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
       name: 'expericePeopleDesc',
       props: {
           peopleDescData: Object
       } 
    }
</script>

<style scoped>
    div#place_people_desc_wrap {
        width:  100%;
        background: #f9f9fa;
    }

    .place_people_desc_box {
        width:  100%;
        padding: 0  0.413rem 1.467rem 0.373rem;
        box-sizing:  border-box;
    }

    .place_people_desc_right {
        width:  100%;
        padding-bottom: 0.827rem;
        text-align:  center;
    }

    .place_people_desc_right_title {
        width:  100%;
        padding: 1.347rem 0 0.8rem;
    }

    p.place_people_desc_right_titleE {
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-size: 0.565rem;
        font-weight: 900;
        font-stretch: normal;
        line-height: 0.665rem;
        color: #22202b;
    }

    p.place_people_desc_right_titleC {
        font-size: 0.24rem;
        line-height: 0.42rem;
        color: #858585;
    }

    .place_people_desc_right_img {
        overflow:  hidden;
        width: 9.213rem;
        height: 8.92rem;
        margin:  0 auto;
    }

    .place_people_desc_right_img img {
        width:  100%;
        height:  100%;
    }

    .place_people_desc_left {
        overflow:  hidden;
        width: 100%;
    }

    .place_people_desc_left_img {
        float:  left;
        overflow:  hidden;
        width: 4.307rem;
        height: 6.52rem;
    }

    .place_people_desc_left_img img {
        width:  100%;
        height:  100%;
    }

    .place_people_name_left {
        float:  right;
        overflow:  hidden;
        width: 4.173rem;
    }

    .place_people_name {
        position:  relative;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-size: 0.64rem;
        font-weight: 900;
        line-height: 0.7rem;
        text-align: right;
        color: #22202b;
    }

    .place_people_name:after {
        position:  absolute;
        left:  0;
        top: 50%;
        content:  '';
        width: 2.4rem;
        height: 0.017rem;
        background-color: #d5d5d8;
    }

    .place_people_desc {
        width:  100%;
    }

    .place_people_descC {
        width:  100%;
        padding-top: 0.787rem;
        font-size: 0.32rem;
        line-height: 0.48rem;
        color: #858585;
    }

    .place_people_descE {
        width: 100%;
        padding-top: 0.707rem;
        font-size: 0.233rem;
        line-height: 0.371rem;
        color: #d6d6d6;
    }
</style>


