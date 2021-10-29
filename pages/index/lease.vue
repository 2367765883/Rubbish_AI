<template>
	<view>
		<view>
			<Citylist :getCity="getCity"></Citylist>
		</view>
		<view  style="margin-bottom: 10px;">
			<special-banner :banner-list="bannerList" :swiper-config="swiperConfig"></special-banner>
		</view>
		<view>
			<FatFatMeng-videolistS-h :videolist="videolisth"></FatFatMeng-videolistS-h>
		</view>
	</view>
</template>

<script>
	import Citylist from '../../components/bazaar-city_list/index.vue'
	import specialBanner from '../../components/EtherealWheat-banner/specialBanner.vue'
	export default{
		components: {
		 specialBanner,
		 Citylist
		 },
		data(){
			return{
				bannerList: [{
				            picture: 'https://pic1.ajkimg.com/display/58ajk/711b4e54ccba40b063e386d09a4cdcfb/640x420c.jpg?t=1',
				            title: '精品房源推荐',
				            description: '三室一厅，位置靠近公园',
				            path: ''
				        }, {
				            picture: 'https://pic3.ajkimg.com/wuba/55fe38cda57e4b8de5783471695ebc68/800x600.jpg?t=1',
				            title: '精品房源推荐',
				            description: '五室两厅，全家入住，无忧无虑',
				            path: ''
				        }, {
				            picture: 'https://pic1.ajkimg.com/display/58ajk/e0014c78e662fadfc5a6a2036485bcb8/640x420c.jpg?t=1',
				            title: '精品房源推荐！',
				            description: '学区房，不在为孩子的教育而担忧',
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
				        image:'https://pic1.ajkimg.com/display/58ajk/1c00b893a73c27d2a4785c6f0b74ab3d/640x420c.jpg?t=1',
				        title:'今日推荐',
				        desc:'电梯房 精装修 ',
				        videotype:0,
				    },
				    {
				        image:'https://pic3.ajkimg.com/wuba/aaa7162b2ee920da5fee7dbb7aa6ccc1/800x600.jpg?t=1',
				        title:'今日推荐',
				        desc:'区政府斜对面中交',
				        videotype:0,
				    },
				    {
				        image:'https://pic1.ajkimg.com/display/58ajk/1bbaa4e772797342eef994a02686c3f7/640x420c.jpg?t=1',
				        title:'今日推荐',
				        desc:'金融北城',
				        videotype:0,
				    },
				    {
				        image:'https://pic1.ajkimg.com/display/58ajk/cc2c5cfb611af8271023e6bb44f32aa3/640x420c.jpg?t=1',
				        title:'今日推荐',
				        desc:'沙冲路地铁口',
				        videotype:0,
				    },
					{
					    image:'https://pic3.ajkimg.com/wuba/10e0d07ae1bdba8f06c084fbb53dd082/800x600.jpg?t=1',
					    title:'今日推荐',
					    desc:'城东新城东站',
					    videotype:0,
					},
					{
					    image:'https://pic3.ajkimg.com/wuba/e3961def24d4d63d50d43a3099b61127/800x600.jpg?t=1',
					    title:'今日推荐',
					    desc:'万科麓山跃层',
					    videotype:0,
					}
				]
			}
		},
		 getCity({city,name}){
		            // city 城市名称
		            // name 定位名称
		        }
	}
	
</script>

<style>
</style>
