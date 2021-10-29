<template>
	<view>
		<view  style="margin-bottom: 10px;">
			<special-banner :banner-list="bannerList" :swiper-config="swiperConfig"></special-banner>
		</view>
		<view>
			<FatFatMeng-videolistS-h :videolist="videolisth"></FatFatMeng-videolistS-h>
		</view>
	</view>
</template>

<script>
	import specialBanner from '../../components/EtherealWheat-banner/specialBanner.vue'
	export default{
		components: {
		 specialBanner
		 },
		data(){
			return{
				bannerList: [{
				            picture: '../../static/img_ch/banner1.png',
				            title: '闲置的东西也是有利用价值的哦',
				            description: '在页面中找到你心仪的东西可以置换',
				            path: ''
				        }, {
				            picture: '../../static/img_ch/banner2.png',
				            title: '让”不要“的东西产生价值',
				            description: '绿色环保也是和谐安宁',
				            path: ''
				        }, {
				            picture: '../../static/img_ch/banner3.png',
				            title: '新年快乐！',
				            description: '新的一年，活力满满',
				            path: ''
				        }],
				        swiperConfig: {
				            indicatorDots: true,
				            indicatorColor: 'rgba(255, 255, 255, .4)',
				            indicatorActiveColor: 'rgba(255, 255, 255, 1)',
				            autoplay: false,
				            interval: 3000,
				            duration: 300,
				            circular: true,
				            previousMargin: '58rpx',
				            nextMargin: '58rpx'
				        },
				videolisth:[
				    {
				        image:'../../static/img_ch/g1.jpg',
				        title:'二手机械键盘',
				        desc:'想换一个鼠标',
				        videotype:0,
				    },
				    {
				        image:'../../static/img_ch/g2.jpg',
				        title:'二手电竞椅子',
				        desc:'想换一个显示器',
				        videotype:0,
				    },
				    {
				        image:'../../static/img_ch/g3.jpg',
				        title:'二手充电宝',
				        desc:'想换一个蓝牙耳机',
				        videotype:0,
				    },
				    {
				        image:'../../static/img_ch/g4.jpg',
				        title:'二手蓝牙耳机',
				        desc:'想换一个充电宝',
				        videotype:0,
				    },
					{
					    image:'../../static/img_ch/g5.jpg',
					    title:'二手蓝Ipad',
					    desc:'想换一个手机',
					    videotype:0,
					},
					{
					    image:'../../static/img_ch/g6.jpg',
					    title:'二手鼠标',
					    desc:'想换一个键盘',
					    videotype:0,
					}
				]
			}
		}
	}
</script>

<style>
</style>
