<template>
	<view class="app">
		<view class="head">
			<view class="headtime">
				<text>等待付款</text>
				<!-- show为true时弹出 -->
				<view class="time" v-if="show">
					14:59
				</view>
				<view v-else class="sesswl" @click="isshow=true">
					查看物流
				</view>
			</view>
			<view class="typetext">
				逾期未支付订单将自动取消
			</view>
			<view class="jzr">
				<view class="jzrbox">
					<image src="../../static/image/gth.png" mode=""></image>
					<text>就诊人： * 旭伟</text>
				</view>
				<view class="grxx">
					<view class="grxxbox">
						<text class="names">支旭伟</text>
						<text class="num">13169678846</text>
					</view>
					<view class="addis">
						广东省珠海市香洲区石花西路格力地产股份有限公司
					</view>
				</view>

			</view>
		</view>
		<view class="card">
			<view class="cardhead">
				<view class="rx">
					Rx
				</view>
				<text>珠海市人民医院互联网医院配送订单</text>
			</view>
			<view class="cardbody">
				<view class="itemsgg">
					<text>
						开喉剑喷雾剂（20ml）
					</text>
					<view>
						¥29.00
					</view>
				</view>
				<view class="itemsff">
					<text>
						用药事项：口服 每次1袋 每天3次
					</text>
					<view>
						x1
					</view>
				</view>

			</view>
			<view class="cardfoot">
				<view class="cfy">
					<view>
						处方药金额：
					</view>
					<text>
						¥50.80
					</text>
				</view>
				<view class="cfy">
					<view>
						快递费：
					</view>
					<text>
						¥10.0
					</text>
				</view>
				<view class="all">
					<view>
						合计:
					</view>
					<text>
						¥60.80
					</text>
				</view>
			</view>
		</view>
		<view class="card">
			<view class="pstime fistpstime">
				<text>
					配送时间：
				</text>
				<view>
					尽快送达 （预计14:32送达）
				</view>
			</view>
			<view class="pstime">
				<text>
					收 货 人：
				</text>
				<view>
					张三 186****8137
				</view>
			</view>
			<view class="dzbox">
				<text class="shdz">
					收货地址：
				</text>
				<view class="dz">
					<text class="dz">
						广东省广东省广东省广东省广东省广东省广东省广东省广东省广东省广东省广东省广东省广东东省广东省广东省广东省广东省广东东省广东省广东省广东省广东省广东东省
					</text>
				</view>
			</view>
		</view>
		<view class="card">
			<view class="pstime fistpstime">
				<text>
					订单编号：
				</text>
				<view class="fzbox">
					0404591164177525
					<view class="fz" @click="copy(0404591164177525)">
						复制
					</view>
				</view>

			</view>
			<view class="pstime">
				<text>
					下单时间：
				</text>
				<view>
					2020-06-03 14:02
				</view>
			</view>
			<view class="dzbox">
				<text class="shdz">
					支付时间：
				</text>
				<view>
					2020-06-03 14:02
				</view>
			</view>
		</view>
		<view class="endfoot">
			<view class="allbox">
				<view>
					合计
				</view>
				<view>
					<text class="fh">
						¥
					</text>
					<text class="qian">
						60.80
					</text>
				</view>
			</view>
			<view class="goend">
				去支付
			</view>
		</view>
		<u-popup v-model="isshow" mode="bottom" border-radius="24">
			<view class="headmd">
				<image class="close" @click="isshow=false" src="../../static/image/clos3x.png" style="width: 48rpx; height: 48rpx;"
				 mode=""></image>
				<text class="address">
					物流信息
				</text>
			</view>
			<view class="xlapp">
				<view class="xlbody">
					<view class="sfbox">
						<image style="width: 32rpx;margin-right: 24rpx;margin-left: 24rpx; height: 32rpx;" src="../../static/image/sf.png"
						 mode=""></image>
						<text> 顺丰速运 594 093 494 467</text>
					</view>
					<view class="fz" @click="copy(0404591164177525)">
						复制
					</view>
				</view>
				<view class="bzt">
					<u-time-line>
						<u-time-line-item nodeTop="2">
							<template v-slot:node>
								<!-- 选中的节点的类名 -->
								<view class="u-node" style="background: #1799FF;">
								</view>
							</template>
							<template v-slot:content>
								<view class="flangs">
									<view class="u-order-title">待取件</view>
									<view class="u-order-desc">您的快件已签收，签收人：支旭伟，如有问题请电联快递员：王进【<text @click="calls" style="color: #1799FF;">15923468964</text>】，投诉电话：0756-6548965</view>
									<view class="u-order-time">08-18 00:27</view>
								</view>
							</template>
						</u-time-line-item>
						<u-time-line-item>
							<template v-slot:content>
								<view class="flangs">
									<view class="u-order-title">派送中</view>
									<view class="u-order-desc">配送员 王进 <text @click="calls" style="color: #1799FF;">15923468964</text>
										正在为您派送，感谢您的耐心等待。</view>
									<view class="u-order-time">08-18 00:27</view>
								</view>
							</template>
						</u-time-line-item>
					</u-time-line>
				</view>
			</view>
		</u-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [],
				show: false,
				isshow: true,
				active: 0
			};
		},
		onLoad() {},
		computed: {},
		methods: {
			calls() {
				uni.makePhoneCall({
					phoneNumber: '110',
					success: (res) => {
						console.log('调用成功!')
					},
					fail: (res) => {
						console.log('调用失败!')
					}

				});
			},
			copy(value) {
				console.log(value)
				uni.setClipboardData({
					data: value + '',
					success: function() {
						console.log('success');
					}
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.bzt {
		margin-left: 84rpx;
		min-height: 500rpx;

	}

	.u-node {
		width: 16rpx;
		height: 16rpx;
		border-radius: 100rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		background: #d0d0d0;
	}

	.u-order-title {
		font-size: 29rpx;
		font-family: PingFang SC;
		font-weight: 500;
		color: rgba(25, 42, 65, 1);
		opacity: 1;
		color: #333333;
	}

	.u-order-desc {
		color: rgb(150, 150, 150);
		margin-bottom: 6rpx;

		font-size: 24rpx;
		font-family: PingFang SC;
		font-weight: 400;
		opacity: 1;

	}

	.u-order-time {
		color: rgb(200, 200, 200);
		position: absolute;
		top: 0;
		left: -130rpx;
		width: 68rpx;
		font-size: 24rpx;
		font-family: SF Pro Text;
		font-weight: 400;
		color: rgba(93, 105, 121, 1);
		opacity: 1;
	}

	.flangs {
		position: relative;

	}

	.xlapp {
		padding: 25rpx 25rpx 0;
		box-sizing: border-box;
	}

	.sfbox {
		display: flex;
		align-items: center;
	}

	.xlbody {
		width: 702rpx;
		height: 88rpx;
		background: rgba(247, 248, 249, 1);
		opacity: 1;
		border-radius: 8rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 48rpx;
	}

	.fz {
		margin-right: 24rpx;
		width: 72rpx;
		height: 36rpx;
		background: rgba(255, 255, 255, 1);
		border: 2rpx solid rgba(93, 105, 121, 1);
		opacity: 1;
		text-align: center;
		line-height: 36rpx;
		margin-left: 24rpx;
		border-radius: 4rpx;
		font-size: 24rpx;
		font-family: PingFang SC;
		font-weight: 500;
		color: rgba(93, 105, 121, 1);
		opacity: 1;
	}

	.address {
		text-align: center;
		width: 100%;
		font-size: 32rpx;
		font-family: PingFang SC;
		font-weight: bold;
		line-height: 112rpx;
		color: rgba(0, 0, 0, 1);
		opacity: 1;
	}

	.headmd {
		text-align: center;
		width: 750rpx;
		position: relative;
		height: 112rpx;

	}

	.close {
		position: absolute;
		top: 32rpx;
		right: 24rpx;
	}

	.endfoot {
		width: 100%;
		height: 112rpx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0px -4rpx 8rpx rgba(51, 51, 51, 0.05);
		opacity: 1;
		display: flex;
		align-items: center;
		justify-content: space-between;
		position: fixed;
		bottom: 0;
		left: 0;

		.allbox {
			display: flex;
			align-items: center;
			margin-left: 24rpx;

			view {
				font-size: 28rpx;
				font-family: PingFang SC;
				font-weight: bold;
				line-height: 34rpx;
				color: rgba(51, 51, 51, 1);
				opacity: 1;
				margin-left: 16rpx;
			}
		}

		.qian {
			font-size: 40rpx;
			width: 142px;
			font-family: SF Pro Text;
			font-weight: 600;
			line-height: 48rpx;
			color: rgba(255, 114, 117, 1);
			opacity: 1;
		}

		.fh {
			font-size: 32rpx;
			width: 142px;
			font-family: SF Pro Text;
			font-weight: 600;
			line-height: 48rpx;
			color: rgba(255, 114, 117, 1);
			opacity: 1;
		}

		.goend {
			text-align: center;
			width: 192rpx;
			height: 72rpx;
			background: rgba(23, 153, 255, 1);
			opacity: 1;
			border-radius: 36rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 500;
			line-height: 72rpx;
			color: rgba(255, 255, 255, 1);
			opacity: 1;
			margin-right: 24rpx;
		}

	}

	.fzbox {
		display: flex;
		justify-content: flex-start;
		align-items: center;

		.fz {
			width: 72rpx;
			height: 36rpx;
			background: rgba(255, 255, 255, 1);
			border: 2rpx solid rgba(93, 105, 121, 1);
			opacity: 1;
			text-align: center;
			line-height: 36rpx;
			margin-left: 24rpx;
			border-radius: 4rpx;
			font-size: 24rpx;
			font-family: PingFang SC;
			font-weight: 500;
			color: rgba(93, 105, 121, 1);
			opacity: 1;
		}
	}

	.dzbox {
		display: flex;
		margin-bottom: 24rpx;
	}

	.dz {
		width: 554rpx;
		font-size: 28rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 40rpx;
		color: rgba(25, 42, 65, 1);
		opacity: 1;
	}

	.sesswl {
		margin-top: 5rpx;
		width: 160rpx;
		height: 64rpx;
		background: rgba(23, 153, 255, 1);
		border: 2rpx solid rgba(255, 255, 255, 1);
		opacity: 1;
		border-radius: 36rpx;
		text-align: center;
		font-size: 29rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 64rpx;
		color: rgba(255, 255, 255, 1);
		opacity: 1;
	}

	.shdz {
		width: 140rpx;
		height: 40rpx;
		font-size: 28rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 40rpx;
		color: rgba(163, 169, 179, 1);
		opacity: 1;
	}

	.all {
		margin-top: 26rpx;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		margin-bottom: 38rpx;

		text {
			margin-left: 10rpx;
			height: 36rpx;
			font-size: 28rpx;
			font-family: SF Pro Text;
			font-weight: 500;
			line-height: 32rpx;
			color: rgba(255, 114, 117, 1);
			opacity: 1;
		}

		view {
			height: 34rpx;
			font-size: 24rpx;
			font-family: PingFang SC;
			font-weight: bold;
			line-height: 34rpx;
			color: rgba(25, 42, 65, 1);
			opacity: 1;
		}
	}

	.cardfoot {
		margin-top: 34rpx;

		.cfy {
			display: flex;
			justify-content: space-between;
			align-items: center;

			view {
				height: 40rpx;
				font-size: 28rpx;
				font-family: PingFang SC;
				font-weight: 400;
				line-height: 40rpx;
				color: rgba(25, 42, 65, 1);
				opacity: 1;
			}

			text {
				height: 36rpx;
				font-size: 28rpx;
				font-family: SF Pro Text;
				font-weight: 300;
				line-height: 32rpx;
				color: rgba(25, 42, 65, 1);
				opacity: 1;
			}
		}
	}

	.cardbody {
		.itemsff {
			margin-top: 12rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;
			margin-bottom: 40rpx;

			text {
				height: 40rpx;
				font-size: 28rpx;
				font-family: PingFang SC;
				font-weight: 400;
				line-height: 40rpx;
				color: rgba(93, 105, 121, 1);
				opacity: 1;
			}

			view {
				height: 38rpx;
				font-size: 32rpx;
				font-family: SF Pro Text;
				font-weight: 400;
				line-height: 38rpx;
				color: rgba(25, 42, 65, 1);
				opacity: 1;
			}
		}

		.itemsgg {
			display: flex;
			justify-content: space-between;
			align-items: center;
		}

		text {
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 500;
			line-height: 40rpx;
			color: rgba(25, 42, 65, 1);
			opacity: 1;
		}

		view {
			height: 36rpx;
			font-size: 28rpx;
			font-family: SF Pro Text;
			font-weight: 400;
			line-height: 32rpx;
			color: rgba(25, 42, 65, 1);
			opacity: 1;
		}
	}

	.rx {
		width: 64rpx;
		height: 36rpx;
		background: rgba(255, 255, 255, 1);
		border: 2rpx solid rgba(207, 215, 225, 1);
		opacity: 1;
		text-align: center;
		border-radius: 4rpx;
		margin-right: 16rpx;
		font-size: 28rpx;
		font-family: SF Pro Text;
		font-weight: 400;
		line-height: 36rpx;
		color: rgba(207, 215, 225, 1);
		opacity: 1;

	}

	.cardhead {
		display: flex;
		align-items: center;

		width: 100%;
		height: 80rpx;
		background: rgba(255, 255, 255, 1);
		opacity: 1;

		text {
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 500;
			line-height: 40rpx;
			color: rgba(207, 215, 225, 1);
			opacity: 1;
		}
	}

	.lsat {
		display: block !important;
	}

	.fistpstime {
		// margin-top: 24rpx;
		padding-top: 24rpx;
	}

	.pstime {
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		width: 702rpx;
		height: 64rpx;
		background: rgba(255, 255, 255, 1);
		opacity: 1;

		text {
			width: 140rpx;
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 500;
			line-height: 40rpx;
			color: rgba(163, 169, 179, 1);
			opacity: 1;
			text-align-last: justify;

			text-align: justify;
			text-justify: distribute-all-lines; // 这行必加，bai兼容ie浏览器
		}

		view {
			height: 40rpx;
			word-wrap: break-word;
			width: 554rpx;
			// height:40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 500;
			line-height: 40rpx;
			color: rgba(25, 42, 65, 1);
		}
	}

	.card {
		margin-top: 24rpx;
		width: 750rpx;
		background: rgba(255, 255, 255, 1);
		oparcity: 1;
		border-radius: 16rpx;
		padding: 0 24rpx 0;
		height: 100%;
		box-sizing: border-box;
	}

	.grxx {
		width: 750rpx;
		height: 144rpx;
		background: rgba(255, 255, 255, 1);
		opacity: 1;
		border-radius: 16rpx;
		padding: 28rpx 0 28rpx 24rpx;
		box-sizing: border-box;
		overflow: hidden;
	}

	.addis {
		height: 40rpx;
		font-size: 28rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 40rpx;
		color: rgba(93, 105, 121, 1);
		opacity: 1;
	}

	.names {
		height: 40rpx !important;
		font-size: 28rpx !important;
		font-family: PingFang SC !important;
		font-weight: 500 !important;
		line-height: 40rpx !important;

		color: rgba(25, 42, 65, 1) !important;
		opacity: 1 !important;
	}

	.grxxbox {
		display: flex;
		align-items: center;
		margin-bottom: 8rpx;

		.num {
			height: 32rpx;
			font-size: 28rpx;
			font-family: SF Pro Text;
			font-weight: 400;
			line-height: 32rpx;
			color: rgba(25, 42, 65, 1);
			opacity: 1;
			margin-left: 24rpx;
		}
	}

	.jzrbox {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 750rpx;
		height: 84rpx;
		border-radius: 16rpx;
	}

	.jzr {
		margin-top: 32rpx;
		background: rgba(232, 245, 255, 1);
		opacity: 1;
		overflow: hidden;
		border-radius: 16rpx;

		image {
			width: 28rpx;
			height: 28rpx;
			margin-right: 16rpx;
		}

		text {
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: bold;
			line-height: 40rpx;
			color: rgba(23, 153, 255, 1);
			opacity: 1;
		}
	}

	.head {
		border-radius: 0 0 16rpx 16rpx;
		position: relative;
		background-color: #1799FF;
		overflow: hidden;

		.headtime {
			padding: 20rpx 24rpx 0;
			box-sizing: border-box;
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 60rpx;
			font-size: 48rpx;
			font-family: PingFang SC;
			font-weight: bold;
			line-height: 60rpx;
			color: rgba(255, 255, 255, 1);
			opacity: 1;
			margin-bottom: 8rpx;
		}

		.typetext {
			padding: 0rpx 24rpx 0;
			box-sizing: border-box;
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 400;
			line-height: 40rpx;
			color: rgba(255, 255, 255, 1);
			opacity: 1;
		}
	}

	.app {
		padding-bottom: 136rpx;
	}
</style>
