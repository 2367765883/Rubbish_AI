<template>
	<view>
		<view  style="margin-bottom: 10px;">
			<special-banner :banner-list="bannerList" :swiper-config="swiperConfig"></special-banner>
		</view>
		<view>
			<view>
				<grid autoplay="true" interval="1000" title="不要的东西也是宝">
					<grid-item iconImg="../../static/img_sq/trade.png" url="change" text="变废为宝"></grid-item>
					<grid-item iconImg="../../static/img_sq/reget.png" url="sell" text="上门回收"></grid-item>
					<grid-item iconImg="../../static/img_sq/help.png" url="home_ser" text="家政服务"></grid-item>
					<grid-item iconImg="../../static/img_sq/lease.png" url="lease" text="房屋出租"></grid-item>
					<grid-item iconImg="../../static/img_sq/tra.png" url="" text="搬家运输"></grid-item>
					<grid-item iconImg="../../static/img_sq/send.png" url="" text="帮忙跑腿"></grid-item>
				</grid>
			</view>
			<div class="test-component">
			    <hm-talk-card :options="options[0]"></hm-talk-card>
		    </div>
			<div class="test-component">
			    <hm-talk-card :options="options[1]"></hm-talk-card>
			</div>
			<div class="test-component">
			    <hm-talk-card :options="options[2]"></hm-talk-card>
			</div>
			<div class="test-component">
			    <hm-talk-card :options="options[3]"></hm-talk-card>
			</div>
		</view>
	</view>
</template>

<script>
	import specialBanner from '../../components/EtherealWheat-banner/specialBanner.vue'
	import HmTalkCard from '@/components/hm-talk-card/index.vue'
	export default {
	    components: { 
		 HmTalkCard,
		 specialBanner
		 },
		data() {
		    return {
				bannerList: [{
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/3_1535359279285.png',
				            title: '七夕将至：时光足够久，韧性也能炖出味',
				            description: '一万年太久，就现在，给你爱',
				            path: ''
				        }, {
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/2_1535359240426.png',
				            title: '新菜上架：无边海洋，找到顺眼的那尾鱼',
				            description: '花中樱，鱼乃鲷花中樱，鱼乃鲷',
				            path: ''
				        }, {
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/1_1535359204228.png',
				            title: '在湘西的烟火气里，发现苗族少女的神明',
				            description: '取材自湘西苗族传统的烟熏文化',
				            path: ''
				        }, {
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/4_1535359327213.png',
				            title: '福利降临，陪伴独自行走的丰盛旅程',
				            description: '在自己的小世界里，日日好日，夜夜好清宵',
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
		      options: [{
		          avator:
		            '/static/hm-talk-card/images/1.png',
		          name: '环保小卢',
		          stateimg:
		            '/static/hm-talk-card/images/img_25252_0_3.png',
		          text: '感谢智能垃圾分类为我的环保行动提供保障！',
		          iconfriendsHelp:
		            '/static/hm-talk-card/images/img_25252_0_0.png',
		          num: '666',
		          like: '点赞',
		          iconTest:
		            '/static/hm-talk-card/images/img_25252_0_1.png',
		          commentNum: '666',
		          comments: '条评论'
		        },
				{
				    avator:
				      '/static/hm-talk-card/images/2.png',
				    name: '环保小刚',
				    stateimg:
				      '/static/hm-talk-card/images/img_25252_0_3.png',
				    text: '旧物还可以互换，按需求来，真的人性化！',
				    iconfriendsHelp:
				      '/static/hm-talk-card/images/img_25252_0_0.png',
				    num: '666',
				    like: '点赞',
				    iconTest:
				      '/static/hm-talk-card/images/img_25252_0_1.png',
				    commentNum: '666',
				    comments: '条评论'
				  },
				  {
				      avator:
				        '/static/hm-talk-card/images/3.png',
				      name: '环保小杨',
				      stateimg:
				        '/static/hm-talk-card/images/img_25252_0_3.png',
				      text: '原来不要的东西可以在这个平台卖给别人，互赢！',
				      iconfriendsHelp:
				        '/static/hm-talk-card/images/img_25252_0_0.png',
				      num: '666',
				      like: '点赞',
				      iconTest:
				        '/static/hm-talk-card/images/img_25252_0_1.png',
				      commentNum: '666',
				      comments: '条评论'
				    },
					{
					    avator:
					      '/static/hm-talk-card/images/4.png',
					    name: '环保小刚',
					    stateimg:
					      '/static/hm-talk-card/images/img_25252_0_3.png',
					    text: '今天把不要的电视机在同城上卖了！',
					    iconfriendsHelp:
					      '/static/hm-talk-card/images/img_25252_0_0.png',
					    num: '666',
					    like: '点赞',
					    iconTest:
					      '/static/hm-talk-card/images/img_25252_0_1.png',
					    commentNum: '666',
					    comments: '条评论'
					  }
				]
		    };
		  },
		 methods:{
		 }	  
	}
</script>

<style scoped>
	page{background-color:#eee;}
	.title{
		text-align: center;
		line-height:4;
		padding-top:var(--status-bar-height);
	}
</style>
