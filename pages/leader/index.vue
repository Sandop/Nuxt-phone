<template>
    <section class="container">
		<div class="leader_said_wrap">
            <div class="leader_said_box">
                <div class="leader_said_position">
                    <div class="leader_said_first">
                        <div class="leader_said_con leader_said_con1">
                            <div class="leader_said_con_img">
                                <img src="~/assets/images/leader/leader_said_01.jpg" alt="">
                            </div>
                            <div class="leader_said_video">
                                <video id="leader_video" controls="controls" preload="auto" poster="http://img.visney.cn/img/banner_img/leader_said_video.jpg">
                                    <source src="http://tbm-auth.alicdn.com/37AVcSkN1FW4wZdPwa7/9IDnBYcymx0wAspfNo2@@hd_hq.mp4?auth_key=1535515053-0-0-ce1500a09241125dabe1fd774ab9c9d5">
                                </video>
                            </div>
                        </div>
                    </div>
                    <div class="leader_said_sec">
                        <div class="leader_said_con leader_said_con3">
                            <img src="~/assets/images/leader/leader_said_03.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con4">
                            <img src="~/assets/images/leader/leader_said_04.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con5">
                            <img src="~/assets/images/leader/leader_said_05.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con6">
                            <img src="~/assets/images/leader/leader_said_06.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con7">
                            <img src="~/assets/images/leader/leader_said_07.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con8">
                            <img src="~/assets/images/leader/leader_said_08.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con9">
                                <img src="~/assets/images/leader/leader_said_09.jpg" alt="">
                            </div>
                        <div class="leader_said_con leader_said_con10">
                            <img src="~/assets/images/leader/leader_said_10.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con11">
                            <img src="~/assets/images/leader/leader_said_11.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con12">
                            <img src="~/assets/images/leader/leader_said_12.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con13">
                            <img src="~/assets/images/leader/leader_said_13.jpg" alt="">
                        </div>
                    </div>
                    <div class="leader_said_third">
                        
                        <div class="leader_said_con leader_said_con14">
                            <img src="~/assets/images/leader/leader_said_14.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con15">
                            <img src="~/assets/images/leader/leader_said_15.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con17">
                            <img src="~/assets/images/leader/leader_said_17.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con18">
                            <img src="~/assets/images/leader/leader_said_18.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con20">
                            <img src="~/assets/images/leader/leader_said_20.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con21">
                            <img src="~/assets/images/leader/leader_said_21.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con22">
                            <img src="~/assets/images/leader/leader_said_22.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con23">
                            <img src="~/assets/images/leader/leader_said_23.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con24">
                            <img src="~/assets/images/leader/leader_said_24.jpg" alt="">
                        </div>
                    </div>
                    <div class="leader_said_fou">
                        <div class="leader_said_con leader_said_con25">
                            <img src="~/assets/images/leader/leader_said_25.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con26">
                            <img src="~/assets/images/leader/leader_said_26.jpg" alt="">
                        </div>
                        <div class="leader_said_con leader_said_con27">
                            <img src="~/assets/images/leader/leader_said_27.jpg" alt="">
                        </div>
                        <div class="leader_said_con28_box">
                            <div class="leader_said_con leader_said_con28">
                                <img src="~/assets/images/leader/leader_said_28.jpg" alt="">
                            </div>
                            <div class="leader_said_letter_btn">
                                <div class="leader_said_letter_btn1" @click="changeLetter1"></div>
                                <div class="leader_said_letter_btn2" @click="changeLetter2"></div>
                            </div>
                            <div class="leader_said_letter1_con" v-if="showLetter1">
                                <div class="leader_said_letter_img">
                                    <div @click="changeLetter1">
                                        <img src="~/assets/images/leader/leader_said_letter1.jpg" alt="" >
                                    </div>
                                </div>
                            </div>
                            <div class="leader_said_letter2_con" v-if="showLetter2">
                                <div class="leader_said_letter_img">
                                    <div @click="changeLetter2">
                                        <img src="~/assets/images/leader/leader_said_letter2.jpg" alt=""  >
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="leader_said_con leader_said_con29">
                            <img src="~/assets/images/leader/leader_said_29.jpg" alt="">
                        </div>
                    </div>
                    <div class="leader_said_fiv">
                        <div class="leader_said_con leader_said_con30">
                            <img src="~/assets/images/leader/leader_said_30.jpg" alt="">
                        </div>
                    </div>
                </div>
            </div>
        </div>
	</section>
</template>

<script>
    export default {
        data (){
            return {
                showLetter1: false,
                showLetter2: false,
            }
        },
        methods: {
            changeLetter1 (){
                this.showLetter1 = !this.showLetter1;
            },
            changeLetter2 (){
                this.showLetter2 = !this.showLetter2;
            }
        },
		head () {
		  return {
		    title:'创始人说',
		    meta: [
		      {name:'keywords',hid: 'keywords',content:'创始人说'},
		      {name:'description',hid:'description',content:'创始人说'}
		    ]
		  }
		}
    }
</script>

<style>
    .leader_said_wrap {
        width: 100%;
    }

    .leader_said_box {
        width: 100%;
    }

    .leader_said_position {
        width: 100%;
    }

    .leader_said_position div {
        width: 100%;
    }

    .leader_said_position>div:nth-child(2n+1) {
        background-color: #f5f6fb;
    }

    .leader_said_position>div:nth-child(2n) {
        background-color: #fff;
    }

    .leader_said_position img {
        width: 100%;
    }

    .leader_said_video {
        width: 100%;
    }

    .leader_said_video video {
        width: 100%;
    }

    .leader_said_con28_box {
        position: relative;
    }

    .leader_said_letter1_con {
        position: fixed;
        top: 0;
        right: 0;
        bottom: 0;
        left:  0;
        background: rgba(0,0,0,0.7);
        z-index: 10086;
        cursor: pointer;
    }

    .leader_said_letter2_con {
        position: fixed;
        top: 0;
        right: 0;
        bottom: 0;
        left:  0;
        background: rgba(0,0,0,0.7);
        z-index: 10086;
        cursor: pointer;
    }

    .leader_said_letter_img {
        overflow-y: auto;
        width:  100%;
        height: 100%;
        margin:  0 auto;
    }

    .leader_said_letter_btn {
        position:  absolute;
        top: 0;
        width:  100%;
        height: 100%;
        z-index: 6;
    }

    .leader_said_letter_btn1 {
        width:  100%;
        height: 6rem;
    }

    .leader_said_letter_btn2 {
        width: 100%;
        height: 7.72rem;
    }

</style>
