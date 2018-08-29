<template>
    <div id="visney_intro_wrap">
			<div class="visney_intro_box">
				<div class="visney_intro_title">
					<div class="visney_intro_titleC"><h2>我们是谁</h2></div>
					<p class="visney_intro_titleE">Who are we?</p>
                    <div class="visney_intro_logo"><img src="~/assets/images/join/new_logo.png"></div>
				</div>
				<div class="visney_intro_culture clearfix">
					<div class="visney_intro_left">
						<ul>
							<li class="visney_intro_left_list">
								<div class="visney_intro_left_title">
									<p class="visney_intro_left_titleC">品牌理念</p>
								</div>
								<div class="visney_intro_left_intro">
									<p>卫诗理，为了你</p>
								</div>
							</li>
							<li class="visney_intro_left_list">
								<div class="visney_intro_left_title">
									<p class="visney_intro_left_titleC">品牌定位</p>
								</div>
								<div class="visney_intro_left_intro">
									<p>一个家庭的高级服务管家，一个生活的居家美学顾问</p>
								</div>
							</li>
							<li class="visney_intro_left_list">
								<div class="visney_intro_left_title">
									<p class="visney_intro_left_titleC">品牌宗旨</p>
								</div>
								<div class="visney_intro_left_intro">
									<p>以家庭为主体，以孩子为中心</p>
									<p>用高质的原创设计产品，通过贵族般的生活仪式，帮助用户获得理想生活</p>
								</div>
							</li>
							<li class="visney_intro_left_list">
								<div class="visney_intro_left_title">
									<p class="visney_intro_left_titleC">品牌使命</p>
								</div>
								<div class="visney_intro_left_intro">
									<p>通过美学教育和生活礼仪，让孩子获得更美好的未来</p>
								</div>
							</li>
						</ul>
					</div>
					
					<div class="visney_intro_right">
						<ul>
							<li class="visney_intro_right_list">
								<div class="visney_intro_right_title">
									<p class="visney_intro_right_titleC">品牌主张</p>
								</div>
								<div class="visney_intro_right_intro">
									<p>品质、品位、仪式感</p>
								</div>
							</li>
							<li class="visney_intro_right_list">
								<div class="visney_intro_right_title">
									<p class="visney_intro_right_titleC">品牌基因</p>
								</div>
								<div class="visney_intro_right_intro">
									<p>礼仪、仪式感、传承、孩子</p>
								</div>
							</li>
							<li class="visney_intro_right_list">
								<div class="visney_intro_right_title">
									<p class="visney_intro_right_titleC">品牌愿景</p>
								</div>
								<div class="visney_intro_right_intro">
									<p>打造家居+生活一站式服务平台</p>
								</div>
							</li>
							<li class="visney_intro_right_list">
								<div class="visney_intro_right_title">
									<p class="visney_intro_right_titleC">品牌调性</p>
								</div>
								<div class="visney_intro_right_intro">
									<p>赋予生活仪式感，让生活艺术化</p>
								</div>
							</li>
						</ul>
					</div>
				</div>
				<div class="visney_intro_details clearfix">
                    <div class="visney_intro_details_img">
						<img src="~/assets/images/join/visney_intro_details_img.png">
					</div>
					<div class="visney_intro_details_left">
						<div class="visney_intro_details_title">
							<p>卫诗理，能为顾客提供的服务是</p>
						</div>
						<div class="visney_intro_details_txt">
							<p>全屋活动家具、全屋定制家具、家居用品</p>
							<p>（窗帘、床品、地毯、挂画、灯具、花艺品、生活用品等自主研发设计）、</p>
							<p>空间硬软装设计、私人活动策划定制等以提供生活品质为基础的服务需求。</p>
						</div>
					</div>
				</div>
			</div>
		</div>
</template>

<script>
    export default {
        name: 'joinVisneyIntro'
    }
</script>

<style scoped>
    div#visney_intro_wrap {
        width:  100%;
        background-color: #f9f9fa;
    }

    .visney_intro_box {
        width:  100%;
        text-align:  center;
    }

    .visney_intro_title {
        width:  100%;
        padding: 1.32rem 0 1.12rem;
    }

    .visney_intro_titleC {
        font-size: 0.64rem;
        font-family: 'Noto Serif CJK SC', 'Source Han Serif SC', 'Source Han Serif', 'source-han-serif-sc','STZhongsong','\5B8B\4F53', 'serif';
        font-weight: 900;
        color: #22202b;
        line-height: 0.64rem;
    }

    p.visney_intro_titleE {
        font-size: 0.24rem;
        line-height: 0.44rem;
        color: #858585;
    }

    .visney_intro_logo {
        overflow:  hidden;
        width: 2.453rem;
        height: 2.533rem;
        margin: 0.88rem auto 0;
    }

    .visney_intro_logo img {
        width:  100%;
        height: 100%;
    }

    .visney_intro_culture {
        display: flex;
        padding: 0 20.688px;
        margin: 0 1.293rem;
        border-bottom: 0.027rem solid rgba(46, 44, 58,0.2);
        box-sizing: border-box;
        text-align: left;
    }

    .visney_intro_culture>div {
        flex:  1;
        width:  50%;
        box-sizing:  border-box;
    }

    .visney_intro_left {
        padding-right: 0.8rem;
    }

    .visney_intro_right {
        padding-left: 0.8rem;
    }

    .visney_intro_culture>div ul {
        width: 100%;
    }

    li.visney_intro_left_list {
        width: 100%;
        height: 4.53rem;
    }

    li.visney_intro_right_list {
        width: 100%;
        height: 4.53rem;
    }

    .visney_intro_left_title {
        width: 100%;
    }

    p.visney_intro_left_titleC {
        font-size: 0.467rem;
        font-weight: bold;
        line-height: 0.5rem;
        color: #22202f;
    }

    .visney_intro_left_intro {
        padding-top: 0.147rem;
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .visney_intro_right_title {
        width: 100%;
    }

    p.visney_intro_right_titleC {
        font-size: 0.467rem;
        font-weight: bold;
        line-height: 0.5rem;
        color: #22202f;
    }

    .visney_intro_right_intro {
        padding-top: 0.147rem;
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .visney_intro_details {
        width:  100%;
        padding: 1.293rem 1.3rem 1.333rem;
        box-sizing:  border-box;
    }

    .visney_intro_details_img {
        width: 7.4rem;
        height: 4.227rem;
        margin:  0 auto;
    }

    .visney_intro_details_img img {
        width:  100%;
        height: 100%;
    }

    .visney_intro_details_left {
        width:  100%;
        padding-top:  0.96rem;
        text-align:  left;
    }

    .visney_intro_details_title {
        font-size: 0.467rem;
        font-weight: bold;
        line-height: 0.5rem;
        color: #22202b;
    }

    .visney_intro_details_txt {
        width:  100%;
        padding-top:  0.453rem;
        font-size: 0.32rem;
        line-height: 0.44rem;
        color: #858585;
    }
</style>


