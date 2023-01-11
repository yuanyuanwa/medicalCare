<template>
	<view class="bg">
		<commonHeader :title="title" :hasBack='true' />
		<view class="flex-between" style="padding: 40rpx 10rpx;">
			<view class="flex-align-center">
				<view class="">
					<image class="image" :src="src2">
					</image>
				</view>
				<view class="font-18">
					<view><text class="font-bold">李小北</text><text style="color:#808080;">（李小北患者）</text></view>
					<view style="color: #3E404D;">地区 地区</view>
				</view>
			</view>
		</view>
		<view class="flex-end p-10">
			<view style="color: #6E707A;">加入问诊室时间：2023/01/11</view>
		</view>
		<view class="flex-between font-18" style="padding: 100rpx 60rpx 30rpx;">
			<view class="" style="color: #6E707A;">
				设置备注
			</view>
			<view class="flex-align-center">
				<view class="" v-if="isEdit">
					<uni-easyinput style="width: 400rpx;" type="text" v-model="name" />
				</view>
				<view class="" v-else>
					111
				</view>
				<uni-icons class='ml-20' @click="edit" type="compose" size="20" color="#6E707A"></uni-icons>
			</view>

		</view>
		<view class="flex-between font-18" style="padding: 70rpx 60rpx 70rpx;">
			<view class="" style="color: #6E707A;">
				个性签名
			</view>
			<view class="">
				爱咋咋地
			</view>
		</view>
		<view class="flex-center">
			<view class="btn">发消息</view>
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
				title: '',
				src2: '../../static/img/111.jpeg',
				isEdit: false,
				name: ''
			}
		},
		methods: {
			edit() {
				this.isEdit = !this.isEdit
			}
		}
	}
</script>

<style lang="scss" scoped>
	.bg {
		height: 100vh;
		background-color: #fcfcfc;
		background-image: linear-gradient(180deg, #dfe8fe 0%, #fcfcfc 100%);
	}

	.image {
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}

	.btn {
		height: 100rpx;
		width: 500rpx;
		background: #5363E3;
		line-height: 100rpx;
		color: #fff;
		border-radius: 50rpx;
		text-align: center;
		font-size: 20px;
	}

	::v-deep .is-input-border {
		height: 50rpx;
		border-radius: 50rpx;
	}
</style>
