<template>
	<view class="box" :style="{height:height}">
		<commonHeader :title="title" :hasBack='true' :bgcolor="'#5878FC'" :color="'white'" />
		<view class="flex-center">
			<view class="card">
				<view class="ball ballLeft"></view>
				<view class="ball ballRight"></view>
				<view class="font-22 text-center pt-20">电子处方签</view>
				<view class="font-14 text-center pt-20 pb-20" style="border-bottom: 2px solid #F0F0FA;">医院医院医院</view>
				<view class="flex-between pt-30 p-20 font-14" style="color: #888989;">
					<view>病例号：2137841</view>
					<view>日期：2022/10/23 09:09:09</view>
				</view>
				<view class="flex-between p-20 font-14">
					<view>姓名：XXX</view>
					<view>性别：男</view>
					<view>年龄：24</view>
				</view>
				<view class="flex-between p-20 font-14">
					<view>科别：XXX</view>
					<view>药费：123</view>
				</view>
				<view class="flex-between p-20 font-14 pb-30" style="border-bottom: 2px solid #F0F0FA;">
					<view>临床诊断：XXXXXXX</view>
				</view>
				<view class="flex-between p-20 font-14">
					<view>Pr：普通药品处方</view>
				</view>
				<view class="pb-80" style='border-bottom: 2px solid #F0F0FA;'>
					<view class="p-20 font-14">
						<view class="flex-between">
							<view class="flex">
								<view class="pr-30">复方含片</view>
								<view>20*9粒/盒</view>
							</view>
							<view>x3</view>
						</view>
						<view class="flex-between font-12" style="color: #888989;">
							<view class="flex">
								<view class="pr-30">用法用量：一次一片，一日三次</view>
							</view>
							<view>￥25.5</view>
						</view>
					</view>
					<view class="p-20 font-14">
						<view class="flex-between">
							<view class="flex">
								<view class="pr-30">复方含片</view>
								<view>20*9粒/盒</view>
							</view>
							<view>x3</view>
						</view>
						<view class="flex-between font-12" style="color: #888989;">
							<view class="flex">
								<view class="pr-30">用法用量：一次一片，一日三次</view>
							</view>
							<view>￥25.5</view>
						</view>
					</view>
					<view class="p-20 font-14">
						<view class="flex-between">
							<view class="flex">
								<view class="pr-30">复方含片</view>
								<view>20*9粒/盒</view>
							</view>
							<view>x3</view>
						</view>
						<view class="flex-between font-12" style="color: #888989;">
							<view class="flex">
								<view class="pr-30">用法用量：一次一片，一日三次</view>
							</view>
							<view>￥25.5</view>
						</view>
					</view>
				</view>
				<view class="p-20 font-14">
					<view class="flex">
						<view class="pr-30">医师：XXX</view>
						<view class="pr-30">药师：XXX</view>
					</view>
					<view class="flex-end pb-50">
						<view class="pr-30">金额：51元</view>
					</view>
					<view>
						<view class="font-12 pl-20 pr-20" style="color: #888989;">
							<view>备注：</view>
							<view>本处方72小时有效</view>
							<view>本处方开前，就诊人已在医院初步确诊</view>
						</view>
					</view>
				</view>
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
				title: 'XXX医生',
				height:0
			}
		},
		onLoad(){
			this.height=uni.getSystemInfoSync().windowHeight+'px';
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.box {
		// height: 100%;
		background: #F0F0FA;
		overflow-y: scroll;
	}

	.card {
		height: 100%;
		width: 90%;
		background: #fff;
		margin-top: 40rpx;
		margin-bottom: 40rpx;
		border-radius: 20rpx;
		box-shadow: 0px 2px 12px 0px #E4E4ED;
		position: relative;
	}

	.ball {
		width: 40rpx;
		height: 40rpx;
		background-color: #F0F0FA;
		border-radius: 50%;
		position: absolute;
		top: 140rpx;
	}

	.ballLeft {
		left: -20rpx;
		box-shadow: -3px -1px 5px 0px #e4e4ed inset;
	}

	.ballRight {
		right: -20rpx;
		box-shadow: 3px 1px 5px 0px #e4e4ed inset;
	}
</style>
