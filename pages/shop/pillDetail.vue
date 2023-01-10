<template>
	<view class="box">
		<commonHeader :title="title" :hasBack='true' :bgcolor="'#fff'" />
		<view style="background-color: #fff;" class="p-20">
			<view class="font-24 pt-30">订单已完成</view>
			<view class="font-17 pt-20">订单已成功支付</view>
		</view>
		<view class="card">
			<view class="pt-20 pb-20">
				<view class="flex-between p-10">
					<view>那谁谁</view>
					<view>188****888</view>
				</view>
				<view class="p-10">哪里哪里哪里哪里</view>
			</view>
		</view>
		<view class="card flex-between" style="padding: 20rpx 20rpx;">
			<view >医生诊断与处方</view>
			<view class="flex-align-center">查看详情<uni-icons type="forward" size="30"></uni-icons></view>
		</view>
	</view>
</template>

<script>
	import commonHeader from '@/components/header/common.vue'
	export default {
		components: {
			commonHeader,
		},
		data() {
			return {
				title: '订单详情'
			}
		},
		methods: {

		}
	}
</script>

<style scoped lang="scss">
	.box {
		background: #F6F8F7;
		height: 95vh;
	}

	.card {
		background-color: #fff;
		border-radius: 16rpx;
		font-size: 18px;
		margin: 20rpx;
		padding: 0rpx 20rpx;
	}
</style>
