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
				            picture: 'https://img10.360buyimg.com/paipai/jfs/t1/167347/22/12172/109385/60505a49Ed111ffdc/60e706df4e67b95a.png',
				            title: '安心交易',
				            description: '任何交易问题在七天内都会得到解决',
				            path: ''
				        }, {
				            picture: 'https://img10.360buyimg.com/paipai/jfs/t1/157598/36/13172/238520/604f32e8Ea5439027/50c2bb97a0b17931.png',
				            title: '官方严选',
				            description: '只为给你更好的宝贝',
				            path: ''
				        }, {
				            picture: 'https://img1.baidu.com/it/u=3591039153,2364240380&fm=26&fmt=auto',
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
