<template>
	<view class="app">
		<view class="head">
			<view class="wrap">
				<u-swiper height='312' :autoplay='false' mode='rect' :list="list" :effect3d="true"></u-swiper>
			</view>
		</view>
		<view class="myorder">
			<view class="fistboxs">
				<image class="rights" src="../../static/image/gj.png" mode=""></image>

				<image class="lefts" src="../../static/image/gj.png" mode=""></image>
				<view class="orcenter">
					<image src="../../static/image/dd.png" mode=""></image>
					<view class="boxtext">
						<view>
							我的处方订单
						</view>
						<text>
							珠海市人民医院药品配送
						</text>
					</view>
				</view>
			</view>
			<view class="secboxs">
				<view class="fywz">
					防疫物资
				</view>
				<view class="sixbox">
					<view class="onebox">
						<image src="../../static/image/qy.png" mode=""></image>
						<view class="onetext">
							<view >
								企业通道
							</view>
							<text>
								企业通道说明文案
							</text>
						</view>
					</view>
					<view class="onebox">
						<image src="../../static/image/gr.png" mode=""></image>
						<view class="onetext">
							<view >
								个人通道
							</view>
							<text>
								个人通道说明文案
							</text>
						</view>
					</view>
					<view class="onebox">
						<image src="../../static/image/xx.png" mode=""></image>
						<view class="onetext">
							<view >
								学校通道
							</view>
							<text>
								学校通道说明文案
							</text>
						</view>
					</view>
					<view class="onebox">
						<image src="../../static/image/xs.png" mode=""></image>
						<view class="onetext">
							<view >
								学生通道
							</view>
							<text>
								学生通道说明文案
							</text>
						</view>
					</view>
					<view class="onebox">
						<image src="../../static/image/ax.png" mode=""></image>
						<view class="onetext">
							<view >
								绿色通道
							</view>
							<text>
								绿色通道说明文案
							</text>
						</view>
					</view>
					<view class="onebox">
						
					</view>
				</view>
			</view>
			<view class="foot">
				<view class="fywz">
					互联网医院
				</view>
				<image class="dw" src="../../static/image/yy.png" mode=""></image>
				<view class="footbox" >
					<image src="../../static/image/bn.png" mode=""></image>
					<view class="foottext">
						<view >
							珠海市人民医院互联网医院
						</view>
						<text>
							在家就能咨询本院专家
						</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						title: '昨夜星辰昨夜风，画楼西畔桂堂东'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						title: '身无彩凤双飞翼，心有灵犀一点通'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
					}
				],
			};
		}
	}
</script>

<style lang="scss">
	.onebox{
		width:50%;
		height:140rpx;
		background:rgba(255,255,255,1);
		opacity:1;
		border-radius:8rpx;
		display: flex;
		align-items: center;
		image{
			width: 72rpx;
			height: 72rpx;
		}
	}
	.onetext{
		margin-left: 26rpx;
		view{
			height: 44rpx;
			font-size:32rpx;
			font-family:PingFang SC;
			font-weight:bold;
			line-height:44rpx;
			color:rgba(51,51,51,1);
			opacity:1;
		}
		text{
			height:34rpx;
			font-size:24rpx;
			font-family:PingFang SC;
			font-weight:400;
			line-height:34rpx;
			color:rgba(153,153,153,1);
			opacity:1;
		}
	}
	.sixbox{
		display: flex;
		justify-content: center;
		align-items: center;
		flex-wrap: wrap;
		
	}
	.fywz {
		width: 702rpx;
		height: 96rpx;
		font-size:36rpx;
		font-family:PingFang SC;
		font-weight:bold;
		line-height:96rpx;
		color:rgba(51,51,51,1);
		opacity:1;
		
	}

	.head {
		margin-top: 24rpx;
	}

	.wrap {
		margin-top: 24rpx;
		margin-bottom: 40rpx;
	}

	.orcenter {
		padding: 48rpx 0 24rpx 24rpx;
		box-sizing: border-box;
		display: flex;
		align-items: center;

		image {
			width: 160rpx;
			height: 128rpx;
		}

		.boxtext {
			margin-left: 32rpx;

			view {
				height: 57rpx;
				font-size: 40rpx;
				font-family: PingFang SC;
				font-weight: bold;
				line-height: 57rpx;
				color: rgba(25, 42, 65, 1);
				opacity: 1;
			}

			text {
				height: 40rpx;
				font-size: 29rpx;
				font-family: PingFang SC;
				font-weight: 500;
				line-height: 40rpx;
				color: rgba(163, 169, 179, 1);
				opacity: 1;
			}
		}
	}
	.foot{
		margin-bottom: 25rpx;
		width: 100%;
		background: rgba(255, 255, 255, 1);
		opacity: 1;
		border-radius: 16rpx;
		position: relative;
		padding:24rpx 0 24rpx 24rpx;
		box-sizing: border-box;
		.dw{
			width: 654rpx;
			height: 144rpx;
			position: absolute;
			bottom: 24rpx;
		}
	}
	.foottext{
		view{
			height:44rpx;
			font-size:32rpx;
			font-family:PingFang SC;
			font-weight:bold;
			line-height:44rpx;
			color:rgba(25,42,65,1);
			opacity:1;
		}
		text{
			height:40rpx;
			font-size:29rpx;
			font-family:PingFang SC;
			font-weight:400;
			line-height:40rpx;
			color:rgba(163,169,179,1);
			opacity:1;
		}
		
	}
	.footbox{
		display: flex;
		align-items: center;
		width:100%;
		height:144rpx;
		margin: 0 auto;
		background:linear-gradient(90deg,rgba(243,250,255,1) 0%,rgba(252,254,255,1) 100%);
		opacity:1;
		border-radius:8rpx;
		image{
			width: 96rpx;
			height: 96rpx;
			margin-right: 24rpx;
			margin-left: 24rpx;
		}
	}
.secboxs{
	margin-bottom: 25rpx;
	width: 100%;
	background: rgba(255, 255, 255, 1);
	opacity: 1;
	border-radius: 16rpx;
	position: relative;
	padding:0 0 0 25rpx;
	box-sizing: border-box;
}
	.myorder {
		padding: 0 24rpx 0;
		box-sizing: border-box;

		.fistboxs {
			margin-bottom: 25rpx;
			width: 100%;
			height: 200rpx;
			background: rgba(255, 255, 255, 1);
			opacity: 1;
			border-radius: 16rpx;
			position: relative;
		}

		.rights {
			position: absolute;
			top: -8rpx;
			left: 25rpx;
			width: 20rpx;
			height: 42rpx;
		}

		.lefts {
			position: absolute;
			right: 25rpx;
			top: -8rpx;
			width: 20rpx;
			height: 42rpx;
		}
	}
</style>
