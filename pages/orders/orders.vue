<template>
	<view class="app">
		<view class="tab">
			<u-tabs class="dx" :list="list" bar-width='24' bar-height='8' font-size='28' inactive-color='black' active-color='#1799FF'
			 :is-scroll="false" :current="currents" @change="change"></u-tabs>
		</view>
		<view class="card">
			<view class="centr">
				<view class="mx">
					<view class="bodysbox">
						<view class="head">
							<view class="headbox">
								<text>订单编号:13132132</text>
							</view>
							<view class="ddnum">
								待付款
							</view>
						</view>
						<view class="center">
							<view class="fistbox">
								<text>
									开喉剑喷雾剂（20ml）
								</text>
								<view>
									¥29.00
								</view>
							</view>
							<view class="secndbox">
								<text>
									用药事项：口服 每次1袋 每天3次
								</text>
								<view>
									x1
								</view>
							</view>
							<view class="treebox">
								共5件商品 实付 ¥50.80
							</view>
						</view>
						<view class="kdf">
							<text>
								快递费：
							</text>
							<view>
								¥10.00
							</view>
						</view>
					</view>
					<view class="foot">
						<view class="leftbtn btn">
							取消订单
						</view>
						<view class="rightbtn btn">
							去支付
						</view>
					</view>
				</view>


				<!-- <view class="asdimg" v-if="showwu">
					<image src="../../static/image/qs.png" mode=""></image>
					<view>
						暂无订单
					</view>
					<text>快去选购吧 !</text>
				</view> -->
			</view>
		</view>
		<!-- <u-loadmore v-if="status=='nomore'?false:true" :is-dot='true' :status="status" /> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				status: 'loadmore',
				zt: null,
				current: 1,
				size: 5,

				total: 0,
				list: [{
						name: '全部'
					},
					{
						name: '待支付'
					}, {
						name: '代发货'
					}, {
						name: '代收货'
					},
					{
						name: '已完成'
					}
				],
				currents: 0
			}
		},
		filters: {

			types(val) {
				if (val == 1) {
					return '已完成'
				} else if (val == 2) {
					return '未付款'
				} else if (val == 3) {
					return '已取消'
				} else {
					return '已付款'
				}
			}
		},
		onReachBottom() {


		},
		async onPullDownRefresh() {

		},
		computed: {
			showwu() {
				// return this.orderlist.length == 0 ? true : false

			},

			typefont(val) {
				if (val == 1) {
					return 'color:#333333'
				} else if (val == 2) {
					return 'color:#FA4D4D'
				} else if (val == 3) {
					return 'color:#999999'
				} else {
					return 'color:#7CC457'
				}
			}
		},
		async onShow() {


		},
		onLoad(val) {


		},

		onHide() {

			this.shows = false
		},
		methods: {
			// 数字补0
			hasDot(num) {
				if (!isNaN(num)) {
					return ((num + '').indexOf('.') != -1) ? num : num.toFixed(2);
				}
			},


			change(index) {
				this.orderlist = []
				this.currents = index;
				this.current = 1
				this.size = 5

			},


		}

	}
</script>


<style lang="scss" scoped>
	.kdf {
		height: 40rpx;
		background: rgba(255, 255, 255, 1);
		opacity: 1;
		text-align: right;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		padding-bottom: 24rpx;
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
			height: 40rpx;
			font-size: 32rpx;
			font-family: SF Pro Text;
			font-weight: 600;
			line-height: 40rpx;
			color: rgba(255, 114, 117, 1);
			opacity: 1;
		}
	}

	.treebox {
		width: 100%;
		height: 72rpx;
		text-align: center;
		background: rgba(252, 253, 253, 1);
		opacity: 1;
		font-size: 24rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 72rpx;
		color: rgba(163, 169, 179, 1);
		opacity: 1;
	}
	.leftbtn{
		width:176rpx;
		margin-right: 16rpx;
		height:64rpx;
		background:rgba(255,255,255,1);
		border:2rpx solid rgba(207,215,225,1);
		opacity:1;
		border-radius:32rpx;
		font-size:24rpx;
		font-family:PingFang SC;
		font-weight:500;
		line-height:64rpx;
		color:rgba(93,105,121,1);
		opacity:1;
	}
	.foot{
		display: flex;
		align-items: center;
		justify-content: flex-end;
		padding-bottom: 24rpx;
	}
	.btn{
		text-align: center;
	}
	.rightbtn{
		width:176rpx;
		height:64rpx;
		background:rgba(255,255,255,1);
		border:2rpx solid rgba(23,153,255,1);
		opacity:1;
		border-radius:32rpx;
		font-size:24rpx;
		font-family:PingFang SC;
		font-weight:500;
		line-height:64rpx;
		color:rgba(23,153,255,1);
		opacity:1;
	}
	.bodysbox{
		background: green;
		border-bottom: 1rpx solid #F1F1F2;
		margin-bottom: 24rpx;
	}
	.secndbox {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 38rpx;

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

	.center {
		// padding: 0 24rpx;
		// box-sizing: border-box;
		width: 100%;
		// height:220rpx;
		background: rgba(255, 255, 255, 1);
		// opacity:1;
		padding-bottom: 32rpx;

	}

	.headbox {
		font-size: 28rpx;
		font-family: SF Pro Text;
		font-weight: 400;
		line-height: 112rpx;
		color: rgba(93, 105, 121, 1);
		opacity: 1;
	}

	.ddnum {
		font-size: 32rpx;
		font-family: PingFang SC;
		font-weight: bold;
		line-height: 112rpx;
		color: rgba(248, 184, 33, 1);
		opacity: 1;
	}

	.head {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		height: 112pxr;
		background: rgba(255, 255, 255, 1);
		opacity: 1;
		box-sizing: border-box;
		margin-top: 24rpx;
	}

	/deep/.u-load-more-wrap {
		background-color: #F7F8F9 !important;
	}

	/deep/.u-more-text {
		background-color: #F7F8F9 !important;
	}

	.onees {
		color: #333333 !important;
	}

	.towes {
		color: #FA4D4D !important;
	}

	.treees {
		color: #999999 !important;
	}

	.forses {
		color: #7CC457 !important;
	}

	.app {
		height: 100%;

	}

	.asdimg {
		height: 100%;
		width: 100%;
		overflow: hidden;

		image {
			display: block;
			width: 262rpx;
			height: 225rpx;
			margin: 300rpx auto 62rpx;
		}

		view {
			width: 100%;
			text-align: center;
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: 400;
			line-height: 28rpx;
			color: rgba(51, 51, 51, 1);
			opacity: 1;
			margin-bottom: 8rpx;
		}

		text {
			width: 100%;
			height: 34rpx;
			display: block;
			text-align: center;
			margin: 0 auto 440rpx;
			font-size: 24rpx;
			font-family: PingFang SC;
			font-weight: 400;
			line-height: 20rpx;
			color: rgba(153, 153, 153, 1);
			opacity: 1;
		}
	}

	/deep/.u-mode-center-box {
		border: 1px solid #E6e6e6;
	}

	.cuiq {
		font-size: 28rpx !important;
	}

	.cuiz {
		font-size: 40rpx !important;
	}

	.hejibox {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.cuiend {
		font-size: 32rpx !important;
	}

	.fistbox {
		width: 100%;
		height: 40rpx;
		font-size: 28rpx;
		margin-bottom: 12rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 40rpx;
		color: rgba(25, 42, 65, 1);
		opacity: 1;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}


	

	.jes {
		display: flex;
		align-items: center;
		font-family: SF Pro Text;
		font-weight: 600;
		color: rgba(250, 77, 77, 1);
		opacity: 1;

		.fh {
			font-size: 20rpx;
			height: 24rpx;
			text-align: center;
		}

		.bw {
			font-size: 32rpx;
			text-align: center;
			line-height: 40rpx;
			height: 40rpx;
		}

		.gw {
			text-align: center;
			font-size: 24rpx;
		}

	}

	.redfont {
		color: red !important;
	}

	.green {
		color: blue;
	}

	.block {
		color: pink;
	}

	.hjjq {
		height: 40rpx;
		font-size: 28rpx;
		margin-right: 15rpx;
		font-family: PingFang SC;
		font-weight: bold;
		line-height: 40rpx;
		color: rgba(51, 51, 51, 1);
		opacity: 1;
	}

	.heji {
		height: 34rpx;
		font-size: 24rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 34rpx;
		color: rgba(51, 51, 51, 1);
		opacity: 1;
	}

	// .center {
	// 	display: flex;
	// 	align-items: center;
	// 	border-bottom: 1rpx solid #E6E6E6;

	// 	.img {
	// 		margin-right: 50rpx;
	// 		margin-left: 4rpx;

	// 		image {
	// 			width: 90rpx;
	// 			height: 96rpx;
	// 		}
	// 	}

	// 	.centerfoot {
	// 		display: flex;
	// 		justify-content: space-between;
	// 		align-items: center;

	// 		.numje {
	// 			height: 40rpx;
	// 			font-size: 24rpx;
	// 			font-family: PingFang SC;
	// 			font-weight: 500;
	// 			line-height: 40rpx;
	// 			color: rgba(153, 153, 153, 1);
	// 			opacity: 1;
	// 			margin-bottom: 0 !important;
	// 		}

	// 		text {
	// 			height: 36rpx;
	// 			font-size: 24rpx;
	// 			font-family: SF Pro Text;
	// 			font-weight: 400;
	// 			line-height: 28rpx;
	// 			color: rgba(51, 51, 51, 1);
	// 			opacity: 1;
	// 		}
	// 	}

	// 	.centerbox {
	// 		width: 100%;
	// 		padding: 24rpx 24rpx 24rpx 0;
	// 		box-sizing: border-box;

	// 		view {
	// 			width: 100%;
	// 			height: 40rpx;
	// 			font-size: 28rpx;
	// 			font-family: PingFang SC;
	// 			font-weight: 500;
	// 			line-height: 40rpx;
	// 			color: rgba(51, 51, 51, 1);
	// 			opacity: 1;
	// 			margin-bottom: 16rpx;
	// 		}
	// 	}

	// }

	.reds {
		color: red !important;
	}

	.tab {

		background: rgba(255, 255, 255, 1);
		box-shadow: 0px 4rpx 8rpx rgba(51, 51, 51, 0.05);
		opacity: 1;
		padding-bottom: 16rpx;
	}



	// .head {
	// 	display: flex;
	// 	flex-wrap: wrap;
	// 	flex-wrap: wrap;
	// 	align-items: center;
	// 	margin-bottom: 12rpx;

	// 	.zftime {
	// 		width: 100%;
	// 		display: flex;
	// 		justify-content: space-between;
	// 		align-items: center;
	// 		height: 48rpx;
	// 		margin-bottom: 20rpx;

	// 		view {
	// 			height: 28rpx;
	// 			font-size: 24rpx;
	// 			font-family: SF Pro Display;
	// 			font-weight: 500;
	// 			line-height: 28rpx;
	// 			color: rgba(153, 153, 153, 1);
	// 			opacity: 1;
	// 		}

	// 		text {
	// 			height: 34rpx;
	// 			font-size: 24rpx;
	// 			font-family: PingFang SC;
	// 			font-weight: bold;
	// 			line-height: 2rpx;
	// 			color: rgba(51, 51, 51, 1);
	// 			opacity: 1;
	// 		}
	// 	}

	// 	.yfk {
	// 		width: 100%;
	// 		display: flex;
	// 		justify-content: space-between;
	// 		align-items: center;
	// 		margin-bottom: 16rpx;

	// 		view {
	// 			font-size: 36rpx;
	// 			font-family: PingFang SC;
	// 			font-weight: bold;
	// 			color: rgba(124, 196, 87, 1);
	// 			opacity: 1;
	// 			height: 50rpx;
	// 			line-height: 50rpx;
	// 		}

	// 		text {
	// 			line-height: 48rpx;
	// 			height: 48rpx;
	// 			font-size: 40rpx;
	// 			font-family: SF Pro Text;
	// 			font-weight: bold;
	// 			color: rgba(51, 51, 51, 1);
	// 			opacity: 1;
	// 		}
	// 	}
	// }


	.imagese {
		width: 40rpx;
		height: 44rpx;
		position: absolute;
		top: 72rpx;
		right: 246rpx;

	}

	/deep/.u-tab-bar {

		background-color: #1799FF !important;
	}

	.bigfont {
		font-weight: 600;
	}



	.box-box {
		display: flex;
		justify-content: center;
		border-bottom: 1px solid #edeef5;

		.box {
			width: 100%;
			height: 88rpx;
			background: rgba(255, 255, 255, 1);
			opacity: 1;
			text-align: center;
			line-height: 88rpx;
		}
	}

	/deep/.u-mask-zoom {
		// background-color: transparent !important;
	}

	.card {
		padding: 0 24rpx 0;
		box-sizing: border-box;

		.centr {
			.mx{
				border-radius: 16rpx;
				padding: 0 24rpx;
				box-sizing: border-box;
				width: 100%;
				background: rgba(255, 255, 255, 1);
				opacity: 1;
				margin-bottom: 32rpx;
			}
		}
	}






	.imagesew {
		width: 40rpx;
		height: 44rpx;
		position: absolute;
		top: 42rpx;
		left: 128rpx;

	}

	.mok {
		position: relative;

		text {
			text-align: center;
			width: 100%;
			font-size: 32rpx;
			font-family: dinbold;
			font-weight: 400;
			color: rgba(255, 255, 255, 1);
			opacity: 1;
		}

		view {
			text-align: center;
			width: 100%;
			font-size: 24rpx;
			margin-top: 6rpx;
			font-family: PingFang SC;
			font-weight: 500;
			color: rgba(255, 255, 255, 1);
			opacity: 1;
		}
	}
</style>
