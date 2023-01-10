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
			<view>医生诊断与处方</view>
			<view class="flex-align-center" @click="toDetail">查看详情<uni-icons type="forward" size="30"></uni-icons>
			</view>
		</view>
		<view class="card">
			<view class="pt-20 pb-40 font-20 pl-10" style="border-bottom: 1px solid gainsboro;">药品信息</view>
			<view class="p-20">
				<view class="font-bold pt-20 pb-20">
					盐酸氟桂胶囊
				</view>
				<view style="color: #888989;" class="pb-40">XXXX生物制药公司</view>
				<view class="flex-between pb-20">
					<view style="color: #888989;">5mg*24粒</view>
					<view>￥14</view>
				</view>
				<view class="flex-between pb-20">
					<view style="color: #888989;">发货不支持退换</view>
				</view>
				<view class="flex-end pb-20" style="border-bottom: 1px solid gainsboro;">
					<view>x1</view>
				</view>
				<view class="flex-between pb-20 pt-20">
					<view style="color: #888989;">商品总金额</view>
					<view>￥14</view>
				</view>
				<view class="flex-between pb-40">
					<view style="color: #888989;">配送费</view>
					<view>￥8</view>
				</view>
				<view class="flex-between pb-20 font-20 font-bold">
					<view>实付总额</view>
					<view style="color: #D43030;">￥22</view>
				</view>
			</view>
		</view>
		<view class="card">
			<view class="pt-20 pb-20 font-20 pl-10">订单信息</view>
			<view class="p-20">
				<view class="flex-between pb-20">
					<view style="color: #888989;">订单编号：12312312</view>
					<view class="copy">复制</view>
				</view>
				<view class="flex-between pb-20">
					<view style="color: #888989;">下单时间：2023-01-10 15：10：19</view>
				</view>
				<view class="flex-between pb-20">
					<view style="color: #888989;">配送方式：送药上门</view>
				</view>
			</view>
		</view>
		<view class="card flex-end" style="padding: 30rpx;">
			<view class="check">
				查看物流
			</view>
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
			toDetail() {
				uni.navigateTo({
					//关闭当前页面，跳转到应用内的某个页面。
					url: '/pages/shop/prescription'
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.box {
		background: #F6F8F7;
		height: 100%;
	}

	.card {
		background-color: #fff;
		border-radius: 16rpx;
		font-size: 18px;
		margin: 20rpx;
		padding: 0rpx 20rpx;
	}

	.copy {
		border: 1px solid #5F99FC;
		padding: 0rpx 30rpx;
		border-radius: 100rpx;
		color: #5F99FC;
	}

	.check {
		padding: 20rpx 40rpx;
		border-radius: 100rpx;
		color: #5F99FC;
		background: #EFF7FF;
		font-weight: bold;
	}
</style>
