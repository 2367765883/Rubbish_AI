<template>
	<view>
		<view class="videobox" :style="[{'background-color':videoboxBackgroundColor}]">
			<view class="videolistS-h" :style="[{'width':videolistWidth}]">
				<view class="videolistS-h-item"
				v-for="(item,index) in  videolist" :key="index"
				>
					<view class="Imagebox">
						<!-- 封面 -->
						<image class="Image" 
						:src="item.image"
						mode="aspectFill"
						></image>
						<!-- 顶部VIP角标||收藏等 -->
						<view class="top" v-if="item.videotype===1">
							<text class="top-text">VIP</text>
						</view>
						<!-- 底部评分等 -->
						<view class="bottom">
							<text class="bottom-text">{{item.jishu}}</text>
						</view>
					</view>
					<view class="videotitle">
						<!-- 标题 -->
						<view class="title">
							<text class="title-text">{{item.title}}</text>
						</view>
						<!-- 摘要 -->
						<view class="desc">
							<text class="desc-text">{{item.desc}}</text>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			// 数据列表
			videolist:{
				type:Array,
				default:[]
			},
			// 外盒子背景色
			videoboxBackgroundColor:{
				type:String,
				default:'rgba(255, 255, 255, .0)'
			},
			// 内盒子宽度
			videolistWidth:{
				type:String,
				default:'710rpx'
			}
		},
		name:"FatFatMeng-videolistS-v",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.videobox {
		/* #ifndef APP-NVUE || APP-PLUS-NVUE */
		display: flex;
		flex-direction: column;
		view{
			display: flex;
		}
		/* #endif */
		width: 750rpx;
		justify-content: center;
		align-items: center;
		.videolistS-h{
			width: 690rpx;
			flex-direction: row;
			flex-wrap: wrap;
			justify-content: space-between;
			.videolistS-h-item {
				width: 340rpx;
				flex-direction: column;
				margin-bottom: 30rpx;
				.Imagebox {
					width: 340rpx;
					height: 220rpx;
					border-radius: 14rpx;
					position: relative;
					.Image,image{
						height: 220rpx;
						border-radius: 14rpx;
						/* #ifdef APP-VUE || H5 || MP */
						width: 100%;
						/* #endif */
						
						/* #ifdef APP-NVUE || APP-PLUS-NVUE */
						width: 340rpx;
						/* #endif */
					}
					.bottom,.top {
						position: absolute;
						right: 0;
					}
					.top{
						top: 0;
						.top-text,.top-text>text {
							padding: 0 8rpx;
							//width: 60rpx!important;
							height: 40rpx!important;
							line-height: 40rpx;
							text-align: center;
							color: #FFFFFF;
							background-color: rgba(193,161,97,0.9);
							//background-color: #ebba73;
							//background-color: #ffa502;
							//background-color: #ff7f50;
							
							//background-color: #ff973f;
							font-size: 28rpx!important;
							//border-radius: 14rpx;
							border-top-left-radius: 0;
							border-top-right-radius: 14rpx;
							border-bottom-right-radius: 0;
							border-bottom-left-radius: 14rpx;
						}
					}
					.bottom{
						bottom: 0;
						.bottom-text,.bottom-text>text {
							padding-bottom: 5rpx;
							padding-right: 10rpx;
							font-size: 26rpx;
							color: #FFFFFF;
						}
					}
				}
				.videotitle {
					height: 70rpx;
					margin-top: 16rpx;
					width: 340rpx;
					flex-direction: column;
					.title{
						height: 40rpx;
						align-items: center;
						/* #ifdef APP-NVUE */
						flex-direction: row;
						flex-wrap: nowrap;
						/* #endif */
						text,.title-text{
							height: 40rpx;
							align-items: center;
							font-size: 32rpx;
							color: #2f3542;
						}
						
					}
					.desc{
						height: 30rpx;
						align-items: center;
						/* #ifdef APP-NVUE */
						flex-direction: row;
						flex-wrap: nowrap;
						/* #endif */
						text,.desc-text{
							height: 30rpx;
							align-items: center;
							font-size: 26rpx;
							color: #747d8c;
						}
						
					}
				}
			}
		}
	}
	.title-text,.desc-text,.title,.desc{
		width: 340rpx;
		max-width: 340rpx;
	}
	text,.title-text,.desc-text,.title,.desc {
		//line-height: 40rpx; max-height: 40rpx;
		overflow: hidden;
		word-break: break-all;  /* break-all(允许在单词内换行。) */
		text-overflow: ellipsis;  /* 超出部分省略号 */
		display: -webkit-box; /** 对象作为伸缩盒子模型显示 **/
		-webkit-box-orient: vertical; /** 设置或检索伸缩盒对象的子元素的排列方式 **/
		-webkit-line-clamp: 1; /** 显示的行数 **/
		lines:1;//NVUE下要用这个属性，来让文字超出隐藏变省略号
	}
</style>
