<template>
	<view class="shopPillBox flex-column-between mb-20">
		<view>
			<view class="p-10 m-20 font-18 shopPillTitle">
				<view class="">
					订单编号：121321
				</view>
			</view>
		</view>
		<view style="flex-grow: 1;padding: 20rpx;color: #888989;">
			<view>订单类型：处方药品</view>
			<view class="flex">
				<view>处方药品：</view>
				<view style="flex-grow: 1;">
					<view v-for="(item,index) in 5" class="flex-between">
					 <view v-if="index<=2">葡萄糖</view>
					 <view v-if="index<=2">￥0.01 x 3</view>
					</view>
					<view>...</view>
				</view>
			</view>
		</view>
		<view>
			<view class="flex-between p-20">
				<view class="font-18">
					状态：已支付
				</view>
				<view class="font-18 font-bold" style="color: #FD9C3B;">
					支付金额：999999
				</view>
			</view>
			<view class="p-20 font-14" style="border-top: 1px solid gainsboro;">开单时间：2023.01.10</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style scoped lang="scss">
	.shopPillBox {
		height: 500rpx;
		background: #F1F3F9;
		border-radius: 10px;
		color: #888989;

	}
	.shopPillTitle {
		border-bottom: 1px solid gainsboro;
	}
</style>
