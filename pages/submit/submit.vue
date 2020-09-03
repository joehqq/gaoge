<template>
	<view class="app">
		<view class="headbox">
			
			<view class="head">
				<view >
					等待付款 
				</view>
				<text>
					14 : 59
				</text>
			</view>
			<view class="header">
				<view class="xinxi">
					<image src="../../static/image/gth.png" mode=""></image>
					<text>
						就诊人： * 旭伟
					</text>
				</view>
				<view class="addressbox">
					<view class="addtext">
						<text>
							格力广场-生活汇商业街
						</text>
						<view class='shr'>
						186****8137	 陈迪强 先生
						</view>
					</view>
					<image src="../../static/image/jt.png" mode=""></image>
				</view>
			</view>
			<view class="zbox">
				<view style="display: flex;height:80rpx ; align-items: center;">
					<view class="rx">
						Rx
						
					</view>
					<text class="zhyy">
						珠海市人民医院互联网医院配送订单
					</text>
				</view>
				<view  style="width: 100%;height: 96rpx; display: flex; justify-content: space-between; align-items: center;">
					<view style="font-size: 28rpx; line-height: 96rpx; color: #192A41; font-weight: 500;">
						处方ID
					</view>
					<view style="font-size: 28rpx; line-height: 96rpx; color: #192A41; font-weight: 500;">
						6564879877
					</view>
				</view>
				<view  style="width: 100%;height: 96rpx; display: flex; justify-content: space-between; align-items: center;">
					<view style="font-size: 28rpx; line-height: 96rpx; color: #192A41; font-weight: 500;">
						快递费
					</view>
					<view style="font-size: 20rpx; line-height: 96rpx; color: #FF7275; font-weight: 500;">
						 ¥10
					</view>
				</view>
				
			</view>
			<view class="zboxs">
				<view  style="width: 100%;height: 96rpx; display: flex; justify-content: space-between; align-items: center;">
					<view style="font-size: 28rpx; line-height: 96rpx; color: #192A41; font-weight: 500;">
						支付方式
					</view>
					<view style="font-size: 28rpx; line-height: 96rpx; color: #192A41; font-weight: 500;">
						微信支付
					</view>
				</view>
			</view>
		</view>
		<view class="foot">
			<view class="all">
				<text style="font-weight: bold;margin-right: 16rpx; color:#192A41;font-size: 28rpx; line-height:112rpx ;">
					合计</text>
				<view style="font-size: 28rpx; color: #ff7275;line-height:112rpx;font-weight: 600;">
                  ¥
				</view>
				<view style="font-size: 40rpx; color: #ff7275;line-height:112rpx;font-weight: 600;">
                10.00
				</view>
			</view>
			<view class="btn">
				去支付
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			backs(){}
		}
	}
</script>

<style scoped lang="scss">
	
	.btn{
		width:192rpx;
		height:72rpx;
		background:rgba(23,153,255,1);
		opacity:1;
		border-radius:36rpx;
		text-align: center;
		line-height: 72rpx;
		
		font-size:28rpx;
		font-family:PingFang SC;
		font-weight:500;
		line-height:72rpx;
		color:rgba(255,255,255,1);
		opacity:1;
	}
	.all{
		display: flex;
		align-items: center;
	}
	.foot{
		position: fixed;
		bottom: 0;
		left: 0;
		width:750rpx;
		height:112rpx;
		background:rgba(255,255,255,1);
		box-shadow:0px -4rpx 8rpx rgba(51,51,51,0.05);
		opacity:1;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding:20rpx 24rpx 20rpx; 
		box-sizing: border-box;
	}
	.zhyy{
		height:40rpx;
		font-size:28rpx;
		font-family:PingFang SC;
		font-weight:500;
		line-height:40rpx;
		color:rgba(207,215,225,1);
		opacity:1;
	}
	.rx{
		text-align: center;
		width:64rpx;
		height:36rpx;
		background:rgba(255,255,255,1);
		border:2rpx solid rgba(207,215,225,1);
		opacity:1;
		border-radius:4rpx;
		font-size:28rpx;
		font-family:SF Pro Text;
		font-weight:400;
		line-height:32rpx;
		color:rgba(207,215,225,1);
		opacity:1;
		margin-right: 14rpx;
	}
	.zboxs{
		margin-top: 24rpx;
		width:100%;
		height:96rpx;
		background:rgba(255,255,255,1);
		opacity:1;
		border-radius:16rpx;
		padding: 0 24rpx 0;
		box-sizing: border-box;
	}
	.zbox{
		margin-top: 24rpx;
		width:100%;
		height:272rpx;
		background:rgba(255,255,255,1);
		opacity:1;
		border-radius:16rpx;
		padding: 0 24rpx 0;
		box-sizing: border-box;
	}
	.backs{
		display: flex;
		justify-content: space-between;
		align-items: center;
		height: 88rpx;
		margin-top: 26rpx;

		image{
			width: 48rpx;
			height: 48rpx;
		}
		text{
			font-size:34rpx;
			font-family:PingFang SC;
			font-weight:bold;
			line-height:48rpx;
			color:rgba(255,255,255,1);
			opacity:1;
		}
	}
	.addtext{
		
	}
	.addressbox{
		width:100%;
		height:176rpx;
		background:rgba(255,255,255,1);
		opacity:1;
		border-radius:16rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 40rpx 24rpx 28rpx;
		box-sizing: border-box;
		image{
			width: 32rpx;
			height: 32rpx;
		}
		text{
			height:50rpx;
			font-size:36rpx;
			font-family:PingFang SC;
			font-weight:bold;
			line-height:50rpx;
			color:rgba(25,42,65,1);
			opacity:1;
		}
		.shr{
			margin-top: 14rpx;
			height:50rpx;
			font-size:28rpx;
			font-family:SF Pro Text;
			font-weight:400;
			line-height:50rpx;
			color:rgba(25,42,65,1);
			opacity:1;
		}
	}
	.xinxi{
		width: 100%;
		height: 84rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		image{
			width: 28rpx;
			height: 28rpx;
			margin-right: 24rpx;
		}
		text{
			font-size:28rpx;
			font-family:PingFang SC;
			font-weight:bold;
			line-height:84rpx;
			color:rgba(23,153,255,1);
			opacity:1;
		}
	}
	.header{
		width:100%;
		background:rgba(232,245,255,1);
		opacity:1;
		border-radius:16rpx ;
	}
	.headbox{
		width:750rpx;
		height:472rpx;
		background:linear-gradient(180deg,rgba(23,153,255,1) 0%,rgba(23,153,255,0.5) 50%,rgba(245,245,245,0) 100%);
		opacity:1;
		padding: 20rpx 24rpx 0;
		box-sizing: border-box;
	}
	.head{
		margin-bottom: 32rpx;
		height:60rpx;
		font-size:48rpx;
		font-family:PingFang SC;
		font-weight:bold;
		line-height:60rpx;
		color:rgba(255,255,255,1);
		opacity:1;
		display: flex;
		align-items: center;
		view{
			margin-right: 24rpx;
		}
	}
 .app,page{
	height: 100%;
	background-color: #F7F8F9;
 }
</style>
