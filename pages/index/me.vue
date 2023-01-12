<template>
	<view class="box">
		<view class="font-22 p-40">我的</view>
		<view class="text-center">
			<image class="image" :src="src">
			</image>
		</view>
		<view class="flex-between font-18" style="padding: 70rpx 60rpx 30rpx;border-bottom: 1px solid gainsboro;">
			<view class="">
				我的工号
			</view>
			<view class="" style="color: #6E707A;">
				1232145
			</view>
		</view>
		<view @click="changePsd" class="flex-between font-18"
			style="padding: 30rpx 60rpx 30rpx;border-bottom: 1px solid gainsboro;">
			<view class="">
				修改密码
			</view>
			<view class="" style="color: #6E707A;">
				<uni-icons type="forward" size="30"></uni-icons>
			</view>
		</view>
		<view class="flex-center">
			<view class="btn" @click="loginOut">退出登录</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: '../../static/img/123.jpeg',
			}
		},
		methods: {
			loginOut() {
				uni.showToast({
					title: '退出成功',
				});		
				setTimeout(()=>{
					uni.navigateTo({
						//关闭当前页面，跳转到应用内的某个页面。
						url: '/pages/login/index'
					});
				},500)
			},
			changePsd() {
				uni.navigateTo({
					//关闭当前页面，跳转到应用内的某个页面。
					url: '/pages/login/changePsd'
				});
			}
		}
	}
</script>

<style scoped>
	.box {
		height: 100%;
		/* background: pink; */
	}

	.image {
		width: 200rpx;
		height: 200rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}

	.btn {
		margin-top: 100rpx;
		height: 100rpx;
		width: 500rpx;
		background: #5363E3;
		line-height: 100rpx;
		color: #fff;
		border-radius: 50rpx;
		text-align: center;
		font-size: 20px;
	}
</style>
