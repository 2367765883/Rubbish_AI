<template>
	<view class="content">
		<view class="uni-padding-wrap uni-common-mt">
					<view>
						<video autoplay="true" loop="true" muted="true" id="myVideo" src="http://vd3.bdstatic.com/mda-mg49q4yn406av51d/360p/h264/1625467882180077163/mda-mg49q4yn406av51d.mp4"
							show-mute-btn="true" @error="videoErrorCallback" :danmu-list="danmuList" enable-danmu danmu-btn controls></video>
					</view>
		</view>
		<grid autoplay="true" interval="1000" title="为您提供最有力的帮助">
			<grid-item iconImg="../../static/img_home/sweep.png" url="" text="卫生打扫"></grid-item>
			<grid-item iconImg="../../static/img_home/nanny.png" url="" text="保姆"></grid-item>
			<grid-item iconImg="../../static/img_home/mather.png" url="" text="月嫂"></grid-item>
			<grid-item iconImg="../../static/img_home/help.png" url="" text="护工"></grid-item>
			<grid-item iconImg="../../static/img_home/cook.png" url="" text="家用厨师"></grid-item>
			<grid-item iconImg="../../static/img_home/marry.png" url="" text="婚介"></grid-item>
		</grid>
		<view class="text">
			<text style="font-style:initial;font-size: 15px;">
				    公司以三高为路线：高标准；高质量；高效率。
					三省为宗旨：省时；省力；省心。
					内部实行六统一营销模式。
					明确了“国际标准管理；精益求精质量；
					满足客户需求；
					积极持续改进”核心方针，以客户至上，全心服务；专业、价值、品质；
					打造现代家政服务品牌。公司主要有室内物品保洁和中高档家具养护及清洁用品研发和制造所组成，随时为客户提供安全、方便、快捷、专业的家政服务。
					
					
					客服电话：888-88888888
			</text>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.text{
		background-color: #CCE6FF;
	}
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
