<template>
	<view>
		<view class="cu-modal " :class="modalName=='Modal'?'show':''">
			<view class="cu-dialog" style="background: none;">
				<view class="count">
					<view class="shop">
						<view class="shop_count" v-for="(item,index) in shop" :key="index">
							<view class="shop_list" v-for="(items,indexs) in item" :key="indexs" @tap="skip(items.goods_id)">
								<view class="shop_list_top">
									<image :src="items.goods_img"></image>
									<view class="name">
										<view>{{items.goods_name}}</view>
									</view>
									
								</view>
								<view class="price">
									<view>活动价:<text>{{items.shop_price}}</text>元</view>
								</view>
							</view>
							
						</view>
						
					</view>
					<view class="cloce" @click="cloce"></view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "welfare",
		props: {
			list: {
				type: Array,
				default: []
			},
			status:{
				type: String,
				default: 'day'
			},
			time:{
				type: Number,
				default: 86400
			}
		},
		data() {
			return {
				modalName:'',
				shop:[]
			};
		},
		created(){
			var that = this;
			that.pushlist();
			that.okrono();
			
		},
		methods:{
			okrono(){
				var that = this;
				var data = new Date().getTime().toString();
				var today = data.substring(0, data.length - 3);
				var dates = new Date(parseInt(today*1000)).getDate();
				uni.getStorage({
				  key: 'welfare_time',
				  success: function (res) {
					  if(that.status=='day'){
						  var todays = new Date(parseInt(res.data*1000)).getDate();
						  if(todays!=dates){
							  that.modalName='Modal'
						  }
					  }else if(that.status=='time'){
						  if(parseInt(res.data)+parseInt(that.time)<parseInt(today) ){
						  		that.modalName='Modal'
						  }
					  }
				  },
				  fail: function (err) {
					that.modalName='Modal'
					
				  }
				});
			},
			pushlist(){
				var that = this;
				setTimeout(() => {
					if( that.list.length!=0){
						for (let i = 0; i < that.list.length; i += 2) {
						  that.shop.push(that.list.slice(i, i + 2))
						}
					}else{
						that.modalName=''
					}
				}, 1000)
				
				
			},
			cloce(){
				this.modalName='';
				var data = new Date().getTime().toString();
				var today = data.substring(0, data.length - 3);
				uni.setStorage({
					key: "welfare_time",
					data: today,
					success: function() {
						
					},
				});
			},
			skip(id){
				this.$emit('skip',id);
			},
		}
	}
</script>

<style lang="scss">
	.count{
		width: 100%;
		height: 75vh;
		margin-top: 10vh;
		margin: 0 auto;
		background-image: url(../static/welfare.png);
		background-size: 100% 100%;
		display: flex;
		position: relative;
		.shop{
			width: 75%;
			height: 38vh;
			margin: 0 auto;
			align-self: center;
			
			.shop_count{
				width: 100%;
				height: 50%;
				display: flex;
				justify-content: space-between;
				.shop_list{
					width: 48%;
					height: 95%;
					background: #fff;
					border-radius: 10rpx;
					
					.shop_list_top{
						width: 100%;
						height: 80%;
						border: 4rpx solid #4ebf75;
						border-radius: 10rpx 10rpx 0rpx 0rpx;
						padding-bottom: 4rpx;
						image{
							width: 100%;
							height: 70%;
						}
						.name{
							width: 100%;
							height: 30%;
							color: #fff;
							text-align: center;
							background: #71cc91;
							border-radius: 10rpx 10rpx 0rpx 0rpx;
							display: flex;
							view{
								width: 100;
								text-align: center;
								font-size: 32rpx;
								align-self: center;
								margin: 0 auto;
								overflow: hidden;
								text-overflow:ellipsis;
								white-space: nowrap;
							}
						}
					}
					.price{
						width: 100%;
						height: 20%;
						display: flex;
						view{
							align-self: center;
							margin: 0 auto;
							color:  #69c98b;
							font-size: 30rpx;
							text{
								color: #fa1b4a;
								font-size: 32rpx;
								font-weight: bold;
								
							}
						}
					}
				
					
				}
			}
			
		}
		.cloce{
			position: absolute;
			bottom: 0rpx;
			width: 20%;
			height: 10vh;
			margin-left: 40%;
		}
	}
</style>
