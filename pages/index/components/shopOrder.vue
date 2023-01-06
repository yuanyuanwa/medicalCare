<template>
	<view class="shopOrderBox flex-column-between mb-20">
		<view class="flex-between p-10 m-20 font-18 shopOrderTitle">
			<view class="">
				订单号：121321
			</view>
			<view class="">
				已完成
			</view>
		</view>
		<view class="flex-align-center">
			<view class="">
				<image class="image" :src="src">
				</image>
			</view>
			<view>
				<view class="">
					<text class="font-18 font-bold">XXX医生</text>
					<text class="object">外科</text>
				</view>
				<view class="">
					问诊时间：2023.02.03-2023.08.16
				</view>
				<view class="">
					问诊类型：电话问诊
				</view>
			</view>
		</view>
		<view class=" p-10 m-20 font-18 shopOrderFoot">
			支付金额：12378312
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// src: 'https://web-assets.dcloud.net.cn/unidoc/zh/shuijiao.jpg'
				src: '../../static/img/123.jpeg'
			}
		},
		methods: {

		}
	}
</script>

<style scoped>
	.shopOrderBox {
		height: 210px;
		background: #F1F3F9;
		border-radius: 10px;

	}

	.shopOrderTitle {
		color: #888989;
		border-bottom: 1px solid gainsboro;
	}

	.shopOrderFoot {
		color: #FD9C3B;
		border-top: 1px dashed gainsboro;
		text-align: right;
		font-weight: bold;
	}

	.image {
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}

	.object {
		display: inline-block;
		padding: 0rpx 20rpx;
		margin: 0rpx 20rpx;
		border-radius: 20rpx;
		color: #5878FC;
		border: 1px solid #5878FC;
	}
</style>
