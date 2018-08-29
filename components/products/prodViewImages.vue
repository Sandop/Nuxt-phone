
<!-- 商品图片组件 -->

<template>
  <div class="products-pic-panel">
    <div class="products-pic-all-box" id="PicZoom">
      <div class="products-pic-show-box" id="BigPic">
        <div class="middle-box" :style="{width: `${boxWidth}%`, height: `${boxHeight}%`}" @mouseenter="isShow = true" @mouseleave="isShow = false" @mousemove="move($event)">
          <img :src="middleImage[curIndex].proImgSrc" :alt="middleImage[curIndex].proImgAlt">
          <div class="move" :style="{width: `${this.glassWidth}px`,height: `${this.glassHeight}px`,top: `${this.glassTop}px`,left: `${this.glassLeft}px`}" v-if="isShow"></div>
        </div>
      </div>
      <div class="products-pic-small-box">
        <div id="SmallPicList" class="products-pic-list-box">
          <ul :style="{width: `${this.ulWidth}rem`,marginLeft: `${this.ulMarginLeft}px`}">
            <li v-for="(image,index) in smallImage" :key="index" :class="{picCur: curIndex == index}" @mouseenter="curIndex = index">
              <img :src="image.proImgSrc" :alt="image.proImgAlt">
            </li>
          </ul>
        </div>
      </div>
      <!-- <div class="b_box" v-if="isShow">
        <img :src="bigImage[curIndex].proImgSrc" :style="{left: `${bigLeft}px`, top: `${bigTop}px`,width: `${this.bigWidth}px`,height: `${this.bigHeight}px`}">
      </div> -->
    </div>
  </div>
</template>

<script>
  export default {
    name: "ProdViewImages",
    props: {
      bigImage: Array,
      middleImage: Array,
      smallImage: Array
    },
    data() {
      return {
        //当前选中商品
        curIndex: 0,
        //是否显示大图
        isShow: false,

        //显示盒子的宽度和高度
        boxWidth: 100,
        boxHeight: 100,

        //显示盒子相对于浏览器窗口的偏移
        boxOffsetLeft: 0,
        boxOffsetTop: 0,

        //放大镜的宽度和高度
        glassWidth: 100,
        glassHeight: 100,

        //放大镜的位置
        glassLeft: 0,
        glassTop: 0,

        //大图的宽度和高度
        bigWidth: 1000,
        bigHeight: 1000,

        //大图的位置
        bigLeft: 0,
        bigTop: 0,

        //小图列表盒子的宽度
        SmallPicListWidth: 460,
        //小图列表li的宽度(加外边距)
        liOuterWidth: 1.816,

        //小图列表ul宽度
        ulWidth: null,

        //小图列表ul的marginleft
        ulMarginLeft: 0
      };
    },
    //初始化
    mounted() {
      this.$nextTick(() => {
        //显示盒子到浏览器窗口最左端的距离
        this.boxOffsetLeft = this.getElementLeft (document.querySelector(".middle-box"));

        //显示盒子到浏览器窗口最顶部的距离
        this.boxOffsetTop = this.getElementTop (document.querySelector(".middle-box"));
        //小图列表ul宽度
        if (this.smallImage.length > 5) {
          this.ulWidth = this.liOuterWidth * this.smallImage.length - 0.133;
        }
      });
    },

    methods: {

     
      //元素最左端到网页最左端的距离
      getElementLeft (element){
        var actualLeft = element.offsetLeft;
        var current = element.offsetParent;
        while (current !== null){
          actualLeft += current.offsetLeft;
          current = current.offsetParent;
        }
        return actualLeft;
      },
      //元素最顶端到网页最顶端的距离
      getElementTop (element){
        var actualTop = element.offsetTop;
        var current = element.offsetParent;
        while (current !== null) {
            actualTop += current.offsetTop;
            current = current.offsetParent;
        }
        return actualTop;
      }
    }
  };
</script>

<style>
  
.products-pic-panel {
	width:  100%;
	height:  100%;
}
.products-pic-all-box {
	position:  relative;
	width: 100%;
	height: 100%;
}
.products-pic-show-box {
	position:  relative;
	overflow:  hidden;
	width:  100%;
	height: 8.36rem;
	background: #f2f2f2;
}
.products-pic-show-box img {
	width:  100%;
	height:  100%;
}

.products-pic-small-box {
	position:  relative;
	overflow:  hidden;
	width:  100%;
	height:  auto;
	margin-top:  0.213rem;
}
.products-pic-list-box {
	overflow:  hidden;
	width:  89%;
	height:  1.6rem;
	margin: 0 auto;
}
.products-pic-list-box ul {
	overflow:  hidden;
	width:  100%;
	height:  100%;
}
.products-pic-list-box ul li {
	float:  left;
	overflow:  hidden;
	width:  1.6rem;
	height:  1.6rem;
	margin: 0 0.081rem;
	background: #f2f2f2;
	border: 0.027rem solid transparent;
	-webkit-box-sizing: border-box;
			box-sizing: border-box;
	cursor: pointer;
}

.products-pic-list-box ul li.picCur {
	border: 0.027rem solid #000;
}
.products-pic-list-box ul li img {
	width:  100%;
	height:  100%;
}
</style>
