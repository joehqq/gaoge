<template>
	<view class="app">
		
		<view class="box">
			<view>收货人</view>
			<input type="text" value="" placeholder="请填写收货人姓名" />
		</view>
		<view class="box">
			<view>手机号</view>
			<input type="text" value="" placeholder="请填写收货人手机号" />
			
		</view>
		<view class="box">
			<view>收货地址</view>
			<input type="text" value="" placeholder="点击选择收获地址" />
			<image @click="show=true" src="../../static/image/jt.png" mode=""></image>
		</view>
		<view class="box">
			<view>门牌号</view>
			<input type="text" value="" placeholder="详细地址，例如：3号楼2单元108" />
		</view>
		<u-popup v-model="show" mode="bottom" border-radius="24">

			<view class="head">
				<image class="close" @click="show=false" src="../../static/image/close.png" style="width: 48rpx; height: 48rpx;" mode=""></image>
				<text class="address">
					选择收货地址
				</text>
			</view>
			<view class="bodysbox">
				<u-radio-group active-color="#1799FF"  v-model="value" @change="radioGroupChange">

					<view class="boxs" v-for="(item, index) in list" :key="index">
						<view class="boxsrs">
							<u-radio :name="item.name" shape="circle" :disabled="item.disabled">
							</u-radio>
							<view class="textbox">
								<text>
									格力广场-生活汇商业街
								</text>
								<view>
									186****8137 陈迪强 先生
								</view>
							</view>
						</view>
						<image class="dzxz" src="../../static/image/dzxx.png" mode=""></image>
					</view>

				</u-radio-group>
			</view>
			<view class="btns">
				<image src="../../static/image/jia.png" mode=""></image>
				<text>新增收货地址</text>
			</view>
		</u-popup>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
				value: false,
				list: [{
						name: 'apple',
						disabled: false
					},
					{
						name: 'banner',
						disabled: false
					},
					{
						name: 'orange',
						disabled: false
					}
				],
				value: 'orange'
			}
		},
		methods: {
			radioGroupChange() {

			}
		}
	}
</script>

<style scoped lang="scss">
	
	.close{
		position: absolute;
		top: 32rpx;
		left: 24rpx;
	}
	
	.btns {
		position: fixed;
		bottom: 16rpx;
		left: 50%;
		transform: translateX(-50%);
		display: flex;
		justify-content: center;
		align-items: center;
		width: 654rpx;
		height: 80rpx;
		background: rgba(23, 153, 255, 1);
		opacity: 1;
		font-size: 32rpx;
		font-family: PingFang SC;
		font-weight: 500;
		line-height: 80rpx;
		color: rgba(255, 255, 255, 1);
		opacity: 1;
		border-radius: 40rpx;

		image {
			width: 32rpx;
			height: 32rpx;

		}

		text {
			margin-left: 16rpx;
		}
	}

	.textbox {
		margin-left: 26rpx;

		text {
			height: 40rpx;
			font-size: 28rpx;
			font-family: PingFang SC;
			font-weight: bold;
			line-height: 40rpx;
			color: rgba(51, 51, 51, 1);
			opacity: 1;
		}

		view {
			font-size: 24rpx;
			font-family: PingFang SC;
			font-weight: 500;
			line-height: 34rpx;
			color: rgba(153, 153, 153, 1);
			opacity: 1;

		}
	}

	.dzxz {
		width: 48rpx;
		height: 48rpx;
	}

	.boxsrs {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.boxs {
		padding: 31rpx 24rpx 32rpx 0;
		box-sizing: border-box;
		width: 100%;
		height: 114rpx;
		display: flex;
		align-items: center;
		position: relative;
		justify-content: space-between;
	}
	
	.bodysbox {
		padding-left: 24rpx;
		box-sizing: border-box;
		min-height: 500rpx;
		padding-bottom: 96rpx;
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

	.head {
		text-align: center;
		width: 750rpx;
		position: relative;
		height: 112rpx;

	}

	input::-webkit-input-placeholder {
		color: #A3A9B3;
		width: 4rpx;
	}

	input {
		caret-color: #1799FF;
		font-size: 29rpx;
	}

	page,
	.app {
		background-color: #FFFFFF;
		height: 100%;
	}

	.box {
		width: 100%;
		height: 96rpx;
		display: flex;
		align-items: center;
		position: relative;

		image {
			position: absolute;
			right: 0;
			width: 48rpx;
			height: 48rpx;
		}


		view {
			width: 144rpx;
			height: 96rpx;
			font-size: 29rpx;
			font-family: PingFang SC;
			font-weight: 400;
			line-height: 96rpx;
			color: rgba(25, 42, 65, 1);
			opacity: 1;

		}
	}

	.app {
		padding: 20rpx 24rpx 0;
		box-sizing: border-box;
	}
</style>
