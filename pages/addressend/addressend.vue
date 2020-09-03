<template>
	<view class="app">
		<image src="../../static/image/cg.png" mode=""></image>
		<view class="zf">
			支付成功
		</view>
		<view class="disk">
			高格健康为您提供送药到家服务
			药品我们会尽快配送
		</view>
		<view class="endsok">
			完成
		</view>
		<view class="backo">
			返回人民医院
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style scoped lang="scss">
	page{
		background-color: #FFFFFF;
		height: 100%;
	}
.app{
	position: relative;
	background-color: #FFFFFF;
	height: 100%;
	.endsok{
		width:542rpx;
		height:80rpx;
		background:rgba(23,153,255,1);
		opacity:1;
		margin: 0 auto 24rpx;
		border-radius:40rpx;
		
		font-size:29rpx;
		font-family:PingFang SC;
		font-weight:500;
		line-height:80rpx;
		color:rgba(255,255,255,1);
		opacity:1;	
			text-align: center;
	}
	.backo{
		width:542rpx;
		height:80rpx;
		background:#F7F8F9;
		opacity:1;
		line-height: 80rpx;
		text-align: center;
		border-radius:40rpx;
		margin: 0 auto;
		text-align: center;
	}
	.disk{
		width:392rpx;
		height:80rpx;
		font-size:29rpx;
		font-family:PingFang SC;
		font-weight:500;
		color:rgba(93,105,121,1);
		margin:0 auto 145rpx ;
		text-align: center;
		opacity:1;
	}
	.zf{
		width:192rpx;
		height:60rpx;
		margin: 0 auto 28rpx;
		font-size:48rpx;
		font-family:PingFang SC;
		font-weight:bold;
		line-height:60rpx;
		color:rgba(25,42,65,1);
		opacity:1;
	}
	image{
		display: block;
		padding-top: 128rpx;
		margin: 0 auto 60rpx;
		width: 114rpx;
		height: 114rpx;
	}
}
</style>
