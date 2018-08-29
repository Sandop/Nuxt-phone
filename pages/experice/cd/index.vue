<template>
	<section class="container">
			<!-- 轮播图部分开始 -->
			<commonBanner :bannerSrc="bannerSrc"></commonBanner>
			<!-- 轮播图部分结束 -->
			
			<!-- Place description satrt -->
			<expericePlaceDesc :placeDescData="placeDescData"></expericePlaceDesc>
			<!-- Place description end -->

			<!-- Place people description satrt -->
			<expericePeopleDesc :peopleDescData="peopleDescData"></expericePeopleDesc>
			<!-- Place people description satrt -->

			<!-- Line Service start -->
			<lineService></lineService>
			<!-- Line Service end -->

			<!-- Panoramic hall start -->
			<expericePanoramic :PanoramicData="PanoramicData"></expericePanoramic>
			<!-- Panoramic hall end -->

			<!-- Native Level start -->
			<expericeStyle :styleData="nativeStyleData"></expericeStyle>
			<!-- Native Level end -->
			
			<!-- Elegant Style start -->
			<expericeStyle :styleData="elegantStyleData"></expericeStyle>
			<!-- Elegant Style end -->

			<!-- Chinese Style start -->
			<expericeStyle :styleData="chineseStyleData"></expericeStyle>
			<!-- Chinese Style end -->

			<!-- Dream Together start -->
			<expericeVideo></expericeVideo>
			<!-- Dream Together end -->
			
			<!-- High Lights start -->
			<expericeHighLights :highLightsData="highLightsData"></expericeHighLights>
			<!-- High Lights end -->
			 
			<!-- Bao Tou Map start -->
			<expericeMap :mapData="mapData"></expericeMap>
			<!-- Bao Tou Map end -->
			
			<!-- Place Address start -->
			<expericeAddress :addressData="addressData"></expericeAddress>
			<!-- Place Address start -->
	</section>
</template>

<script>
	import axios from 'axios'
	import commonBanner from '~/components/common/commonBanner'
	import expericePlaceDesc from '~/components/experice/expericePlaceDesc'
	import expericePeopleDesc from '~/components/experice/expericePeopleDesc'
	import lineService from '~/components/experice/lineService'
	import expericePanoramic from '~/components/experice/expericePanoramic'
	import expericeStyle from '~/components/experice/expericeStyle'
	import expericeHighLights from '~/components/experice/expericeHighLights'
	import expericeMap from '~/components/experice/expericeMap'
	import expericeVideo from '~/components/experice/expericeVideo'
	import expericeAddress from '~/components/experice/expericeAddress'

	export default {
		data (){
			return {
				bannerSrc: 'http://img.visney.cn/img/nuxtPhone/expericecd/banner.png',
				placeDescData: {
					placeDescTitle: '成都',
					placeDescTitleE: 'Cheng Du',
					placeDesc: '成都，四川省省会，简称“蓉”。是四川省的政治、经济和文化中心，素有“天府之国”“美食之都”的美誉',
					placeDescImgSrc: [
						'http://img.visney.cn/img/nuxtPhone/expericecd/place_desc_right1.png','http://img.visney.cn/img/nuxtPhone/expericecd/place_desc_right2.png','http://img.visney.cn/img/nuxtPhone/expericecd/place_desc_right3.png','http://img.visney.cn/img/nuxtPhone/expericecd/place_desc_right4.png'
					],
					placeDescImgName: ['峨眉山','九寨沟','稻城亚丁','蜀绣']
				},
				peopleDescData: {
					peopleDescTitleCn: 'CHENGDU',
					peopleDescTitleEn: '成都卫诗理体验馆',
					placeImgSrc: 'http://img.visney.cn/img/nuxtPhone/expericecd/place_people_desc_right_img.png',
					peopleName: '苏轼',
					peopleImgSrc: 'http://img.visney.cn/img/nuxtPhone/expericecd/place_people_desc_left_img.png',
					peopleDescCn: '“莫听穿林打叶声，何妨吟啸且徐行。竹杖芒鞋轻似马，谁怕？-蓑烟雨任平生”',
					peopleDescEn: '"Do not listen to the sound of beating leaves through the forest. Bamboo stick mango shoes light as a horse, who is afraid? "'
				},
				PanoramicData: {
					PanoramicTitleCn1: '成都体验馆',
					PanoramicTitleCn2: '唯美实景曝光',
					PanoramicTitleEn: 'Panoramic hall',
					PanoramicTitleDesc: '馆内产品实景展示，呈现空间艺术的美感，让生活处处皆美学',
					PanoramicListData: [
						{
							PanoramicListTitle: '致敬·先锋',
							PanoramicListIntro: '中高端空间美学MYD设计团队匠心呈现，缔造纯正欧美贵族古典风范。',
							PanoramicListIntroEn: 'Professional team',
							PanoramicListImg: 'http://img.visney.cn/img/nuxtPhone/expericecd/panoramic_hall_list_img1.png',
						},
						{
							PanoramicListTitle: '诚献·臻品',
							PanoramicListIntro: '2400㎡生态生活体验馆，1135款臻尚奢品，风格涵盖现代美式、后现代美式、欧式、英式、轻奢小法、禅意中式、新古典、中式、北欧等海量精品供您臻选',
							PanoramicListIntroEn: 'Quality products',
							PanoramicListImg: 'http://img.visney.cn/img/nuxtPhone/expericecd/panoramic_hall_list_img2.png',
						}
					]
				},
				nativeStyleData: {
					styleTitle: '体验馆 第一层',
					styleDesc: ['麦巴赫·纽约摩登系列','美的产品传递出来的是人和世界的理解'],
					styleImg: [
						'http://img.visney.cn/img/nuxtPhone/expericecd/native_level_list1.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/native_level_list2.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/native_level_list3.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/native_level_list4.png'
					],
					styleMore: false
				},
				elegantStyleData: {
					styleTitle: '体验馆 第二层',
					styleDesc: ['麦巴赫·纽约摩登系列','宾丽·美式简奢系列  比弗利·新现代轻奢系列','爱把简单生活过成甜'],
					styleImg: [
						'http://img.visney.cn/img/nuxtPhone/expericecd/chinese_style_list1.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/chinese_style_list2.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/chinese_style_list3.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/chinese_style_list4.png'
					],
					styleMore: false
				},
				chineseStyleData: {
					styleTitle: '体验馆 第三层',
					styleDesc: ['丘吉尔庄园·英式名流系列 杜兰戈美式系列','梵地亚欧式II系列  翡丽·后现代高端艺术系列','愈品味，愈懂品味'],
					styleImg: [
						'http://img.visney.cn/img/nuxtPhone/expericecd/natural_style_list1.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/natural_style_list2.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/natural_style_list3.png',
						'http://img.visney.cn/img/nuxtPhone/expericecd/natural_style_list4.png'
					],
					styleMore: true
				},
				highLightsData: {
					highLightsTitleCn1: '卫诗理成都体验馆',
					highLightsTitleCn2: '六大专属亮点',
					highLightsTitleEn: 'Olivelife',
					highLightsList: [
						{
							highLightsListNum: '01',
							highLightsListTitle: '欧奢软装',
							highLightsListTitleEn: 'European luxury soft outfit',
							highLightsListDesc: '纯真欧美软装搭配，回溯一个时代的繁华',
							highLightsListImg: 'http://img.visney.cn/img/nuxtPhone/expericebt/high_lights_list_img1.png',
						},
						{
							highLightsListNum: '02',
							highLightsListTitle: '生态绿植',
							highLightsListTitleEn: 'Ecological green plant',
							highLightsListDesc: '纯粹生态，自然礼遇，缔造都市里的绿野仙踪',
							highLightsListImg: 'http://img.visney.cn/img/nuxtPhone/expericebt/high_lights_list_img2.png',
						},
						{
							highLightsListNum: '03',
							highLightsListTitle: '安神香薰',
							highLightsListTitleEn: 'Nerves aromatherapy',
							highLightsListDesc: '法国南部香水之都格拉斯特配香薰',
							highLightsListImg: 'http://img.visney.cn/img/nuxtPhone/expericebt/high_lights_list_img3.png',
						},
						{
							highLightsListNum: '04',
							highLightsListTitle: '特配餐饮',
							highLightsListTitleEn: 'Especially with the dining',
							highLightsListDesc: '舌尖上的包头，蒙古包的美食',
							highLightsListImg: 'http://img.visney.cn/img/nuxtPhone/expericecd/high_lights_list_img4.png',
						},
						{
							highLightsListNum: '05',
							highLightsListTitle: '免费接送',
							highLightsListTitleEn: 'Free Shuttle',
							highLightsListDesc: '在线预约，尊享高铁站、机场专人专车服务',
							highLightsListImg: 'http://img.visney.cn/img/nuxtPhone/expericebt/high_lights_list_img5.png',
						},
						{
							highLightsListNum: '06',
							highLightsListTitle: '精致伴手礼',
							highLightsListTitleEn: 'Set fine',
							highLightsListDesc: '为每一位卫诗理尊贵客户准备的专属伴手礼',
							highLightsListImg: 'http://img.visney.cn/img/nuxtPhone/expericebt/high_lights_list_img6.png',
						}
					]
				},
				mapData: {
					longitude: 103.9864779602,
					latitude: 30.6127248839,
					title: '成都体验店',
					description: '地址：成都市武侯区首信红星国际广场1号楼卫诗理家具旗舰店'
				},
				addressData: {
					addressDetils: ['成都市武侯区首信红星国际广场1号楼卫诗理家具旗舰店', '距离双流机场8公里，驾车需17分钟', '距离火车站成都站20公里，驾车需38分钟', '距离火车站成都东站21公里，驾车需40分钟'],
					hotLineTitle: '线下招商热线：',
					hotLineNum: '400 900 6267',
					phoneTitle: '预约电话（李姐 Lecoo）',
					phoneNum: '15884588477',
					contentNum: '02885007888',
					contentPeople: ''
				}
			}
		},
		components: {
			commonBanner,
			expericePlaceDesc,
			expericePeopleDesc,
			lineService,
			expericePanoramic,
			expericeStyle,
			expericeHighLights,
			expericeMap,
			expericeVideo,
			expericeAddress
		},
		head () {
		  return {
		    title:this.metaData.navigationTitle,
		    meta: [
		      {name:'keywords',hid: 'keywords',content:`${this.metaData.navigationKeyword}`},
		      {name:'description',hid:'description',content:`${this.metaData.navigationDescription}`}
		    ],
			script: [
				{src:'http://api.map.baidu.com/api?v=2.0&ak=MDdqxkqhQzfdBzfu2tfGiidGbHgTfGrB'}
			]
		  }
		},
		async asyncData({params,store}){
			//head信息
			let metaData = await axios(`${store.state.wordpressAPI}/NavigationMeta/get/21`);
			return {
				metaData: metaData.data,
			} 
		}
	}
</script>
