 <template>
	<view class="content">
		<uni-popup ref="popup" type="bottom">
			<view>
				<scroll-view show-scrollbar="true" scroll-y="true" class="s-c-list-x">
					<view v-for="item  in all" id="demo1" class="scroll-view-item uni-bg-red">
						<view style="color:#FFFFFF; width: 100%;height: 30px;background-color:#5351FB">{{item.name}}&nbsp&nbsp&nbsp&nbsp{{item.type}}</view>
					</view>
				</scroll-view>
			</view>
		</uni-popup>
		
		
		<view style="margin-top: 10px;">
		        <lv-select
				v-model="searchtxt"
		        @handleSearch = "handleSearch"
				@photo = "photo"
		        placeholder = "拍照识别请点击左边放大镜"
		        type = "primary"
		        ></lv-select>
		</view>
		<view style="text-align: left;font-size: 14px;color: #666;margin-top:10px;background:#f2f2f2;padding:5px;border-radius:5px;">
								<text>
									请完整地输入垃圾的中文名称（包括材质），如：牛奶盒，旧衣服，塑料瓶。拍照时需保证光线充足，查询以图片识别结果为准，多个物品无法同时识别。本查询系统仅供参考，具体分类以所属专业的管理部门条例为准。
								</text>
		</view>
		<view style="padding: 30px 0px 0px 0px;display: flex;justify-content: space-between;flex-wrap: wrap;font-size: 16px;">
			<view @click="wet()" style="width:50%;text-align: center;margin-bottom: 10px;color: #8b3f2c;">
				<image src="../../static/types/typeicon_1.png" style="width:120px;" mode="widthFix"></image>
				<view>{{name[0]}}</view>
			</view>
			<view @click="dry()" style="width:50%;text-align: center;margin-bottom: 10px;color: #363636;">
				<image src="../../static/types/typeicon_2.png" style="width:120px;" mode="widthFix"></image>
				<view>{{name[1]}}</view>
			</view>
			<view @click="reuse()" style="width:50%;text-align: center;margin-bottom: 10px;color: #1e25b0;">
				<image src="../../static/types/typeicon_3.png" style="width:120px;" mode="widthFix"></image>
				<view>{{name[2]}}</view>
			</view>
			<view @click="Harmful()" style="width:50%;text-align: center;margin-bottom: 10px;color: #c6242c;">
				<image src="../../static/types/typeicon_4.png" style="width:120px;" mode="widthFix"></image>
				<view>{{name[3]}}</view>
			</view>
		</view>		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				many:[],
				name:["湿垃圾","干垃圾","可回收物","有害垃圾"],
				imgPath:"",
				keyword:"",
				searchresult:null,
				searchtxt:"",
				Listname:[],
				Listtype:[],
				all:[
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					},
					{
						name:"",
						type:"",
						
					}
				]
			}
		},
		onLoad() {
		},
		methods: {
			photo(){
				this.searchtxt=""
				this.getPhoto()
			},
			dry(){
				uni.navigateTo({
					url:"dry"
				})
			},
			wet(){
				uni.navigateTo({
					url:"wet"
				})
			},
			reuse(){
				uni.navigateTo({
					url:"reuse"
				})
			},
			Harmful(){
				uni.navigateTo({
					url:"Harmful"
				})
			},
			// 从相机获取照片
			getPhoto(){
			    this.searchtxt=""
				uni.chooseImage({
					count:1,
					success: (res) => {
						console.log("获取照片成功");
						this.imgPath=res.tempFilePaths[0];
						console.log(this.imgPath)
						res.tempFilePaths[0]=null;
						console.log(this.imgPath)
						this.imgtobase64();
					}
				})
				// this.imgtobase64() 
				// this.flag=false;
			},
			imgtobase64(){
				uni.getFileSystemManager().readFile({
					filePath:this.imgPath,
					encoding:"base64",
					success:(res)=>{
						// console.log("这里是"+res.data);
						console.log("base64是"+res.data)
						this.imgsend(res.data)
					}
				});
			},
			async imgsend(bs64){
				// 请求得到acces_token
				var [error,res] = await uni.request({
					url:"https://aip.baidubce.com/oauth/2.0/token?grant_type=client_credentials&client_id=GiYzMNaUCfGWF9q2Blzc11KD&client_secret=tb1d7F1Es5YGz1jG5uoBppTqaB8ePC9d",
				});
				var access_token = res.data.access_token;
				// 请求到图像识别
				var [error,res] = await uni.request({
					url:"https://aip.baidubce.com/rest/2.0/image-classify/v2/advanced_general",
					method:"POST",
					data:{
						image:bs64,
						access_token:access_token,
					},
					header:{
						"Content-Type":"application/x-www-form-urlencoded",
					}
				})
				// 打印请求得到的结果
				// console.log(res);
				console.log("请求成功")
				console.log(res.data.result)
				this.getresult(res.data.result);
			},	
			getresult(result){
				console.log("进入此步")
				var sure_resultId;
				console.log("长度是"+result.length)
				for(var i=0;i<result.length;i++){
					if(result[i].score>.7){
						 sure_resultId=i;
						 break;
					}
					this.many.push(result[i])
				};
				if(sure_resultId>=0){
					console.log("key"+result[sure_resultId].keyword)
					this.searchwhat(result[sure_resultId].keyword);
				}
				uni.showActionSheet({
					itemList:this.many,
					success: (res) => {
						this.searchwhat(result[res.tapIndex].keyword)
					}
				})
			},
			searchwhat(wt){
				uni.showLoading({
						title: '正在查询请稍后',
						duration: 1500,
						mask: true
				})
				uniCloud.callFunction({
					name:"TrashClassify",
					data:{
						keyword:wt,
					},
					 success: (res) => {
						console.log("请求成功"+res.result),
						this.searchresult=res.result;
						console.log("长度是"+this.searchresult.similars.length)
						for(var k=0;k<this.searchresult.similars.length;k++){
							if(this.searchresult.similars.length==0){
								uni.showToast({
									   title: '没有查询到结果',
									   icon: 'none',
									   duration: 2000
								}) 
							}
							this.Listname[k]=this.searchresult.similars[k].keywords;
							this.Listtype[k]=this.searchresult.similars[k].typename;
							this.all[k].name=this.Listname[k];
							this.all[k].type=this.Listtype[k];
						}
						this.$refs.popup.open('bottom')
						console.log(this.all)
					}
				})
			},
			handleSearch() {
			    this.searchwhat(this.searchtxt);
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.s-c-list-x{
	        white-space: nowrap;
	        width: 100%;
	        height: 450upx;
	        background-color: #1abc9c;
	        color:#fff;
	        overflow: hidden;
	        border-radius: 10upx;
	    }
</style>
