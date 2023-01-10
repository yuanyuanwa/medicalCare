<template>
	<view class="m-20 box">
		<commonHeader :title="title" :hasBack='true' :bgcolor="'#fff'" />
		<view style="background-color: #fff;">
			<view class="font-24 pt-30">订单已完成</view>
			<view class="font-17 pt-20">问诊结束，您可以再次发起问诊</view>
			<view class="flex-center pt-40 pb-40" style="width: 100%;border-bottom: 1px solid gainsboro;">
				<view class="btn" @click="checkAgain">再次问诊</view>
			</view>
		</view>
		<view style="background-color: #fff;" class="font-18">
			<view class="pt-30 pb-20 flex-center">
				<view style="color:#888989;">订单类型</view>
				<view style="flex-grow: 1;padding-left: 50rpx;">电话问诊（ 20元 ）</view>
			</view>
			<view class="">
				<view style="color:#888989;">
					接诊医生
				</view>
				<view class="card flex-align-center">
					<view class="">
						<image class="image" :src="src">
					</view>
					<view>
						<view class="flex-align-center">
							<view class="">
								XXX医生
							</view>
							<view class="font-14 pl-20">
								主任医师
							</view>
						</view>
						<view class="flex-align-center font-14 pt-20">
							<view class="">
								医院医院医院医院医
							</view>
							<view class="font-14 pl-20">
								科室
							</view>
						</view>
					</view>
				</view>
				<view class="flex-between pt-40 pb-40" style="border-bottom: 1px solid gainsboro;">
					<view>
						<view class="">
							您对这次服务满意吗？
						</view>
						<view style="color: #888989;" class="font-14">您的评价会让医生做得更好</view>
					</view>
					<view class="flex-center">
						<view class="iconfont icon-manyi font-28 font-bold pr-20 pl-20" style="color: #F0AD4E;"></view>
						满意<view class="iconfont icon-bumanyi font-28 font-bold pr-20 pl-20" style="color: #F0AD4E;">
						</view>不满意
					</view>

				</view>
				<view class="pt-30 pb-20 flex-center" style="border-bottom: 1px solid gainsboro;">
					<view style="color:#888989;">患者信息</view>
					<view style="flex-grow: 1;padding-left: 50rpx;">XXX 女 24岁</view>
				</view>
				<view class="pt-30 pb-20 flex-center" style="border-bottom: 1px solid gainsboro;">
					<view style="color:#888989;">就诊情况</view>
					<view style="flex-grow: 1;padding-left: 50rpx;">已开处方</view>
				</view>
				<view class="pt-30 pb-20 flex-center" style="border-bottom: 1px solid gainsboro;">
					<view style="color:#888989;">病情描述</view>
					<view style="flex-grow: 1;padding-left: 50rpx;">发烧到39度怎么办</view>
				</view>
			</view>
		</view>
		<view style="background-color: #fff;" class="font-18 mt-20">
			<view class="pt-30 pb-20 flex-center">
				<view style="color:#888989;">订单号码</view>
				<view style="flex-grow: 1;padding-left: 50rpx;">987987987</view>
			</view>
			<view class="pt-30 pb-20 flex-center">
				<view style="color:#888989;">下单时间</view>
				<view style="flex-grow: 1;padding-left: 50rpx;">2023-12-05 14:10:20</view>
			</view>
			<view class="pt-30 pb-20 flex-center" style="border-bottom: 2px dashed gainsboro;">
				<view style="color:#888989;">订单号码</view>
				<view style="flex-grow: 1;padding-left: 50rpx;">987987987</view>
			</view>
			<view class="pt-30 pb-20 flex-center">
				<view style="color:#888989;">支付时间</view>
				<view style="flex-grow: 1;padding-left: 50rpx;">2023-12-05 14:10:20</view>
			</view>
			<view class="pt-30 pb-20 flex-center">
				<view style="color:#888989;">支付方式</view>
				<view style="flex-grow: 1;padding-left: 50rpx;">微信支付</view>
			</view>
			<view class="pt-30 pb-20 flex-between">
				<view class="flex">
					<view style="color:#888989;">开票信息</view>
					<view style="padding-left: 50rpx;">暂未开票</view>
				</view>
				<view class="ticket">
					申请开票
				</view>
			</view>
		</view>
		
		<view style="background-color: #fff;height: 100rpx;line-height: 100rpx;" class="font-20 mt-40 text-center">联系医生</view>
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
				title: '订单详情',
				src: '../../static/img/123.jpeg'
			}
		},
		methods: {
			checkAgain() {
				uni.navigateTo({
					//关闭当前页面，跳转到应用内的某个页面。
					url: '/pages/shop/doctor?id=1',
					// 此方式只是适合 uni.navigateTo() 方法
					success: function(res) {
						res.eventChannel.emit('argParams', {
							id: '100',
							name: '菠萝'
						})
					}
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.btn {
		height: 90rpx;
		line-height: 90rpx;
		border-radius: 50rpx;
		width: 550rpx;
		font-size: 18px;
		background: #5878FC;
		color: white;
		text-align: center;
	}

	.box {
		background: #F4F3F3;
		height: 100%;
	}

	.card {
		height: 190rpx;
		width: 100%;
		background: #F5F7F6;
		border-radius: 20rpx;
		margin-top: 10rpx;
	}

	.image {
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}

	.ticket {
		width: 200rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		border: 1px solid #5878FC;
		border-radius: 30rpx;
	}
</style>
