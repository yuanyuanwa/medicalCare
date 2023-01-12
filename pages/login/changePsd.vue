<template>
	<view>
		<commonHeader :title="title" :hasBack='true' />
		<view class="p-30">
			<uni-forms :modelValue="formData" label-position="top" :rules="rules" ref="form" :labelWidth='140'>
				<uni-forms-item label="旧密码:" name="code">
					<input class="input" type="password" v-model="formData.code" placeholder="请输入旧密码" />
				</uni-forms-item>
				<uni-forms-item label="新密码:" name="newPassword">
					<input autocomplete="new-password " class="input" type="password" v-model="formData.newPassword"
						placeholder="请输入新密码" />
				</uni-forms-item>
				<uni-forms-item label="确认新密码:" name="passwordTwo">
					<input class="input" type="password" v-model="formData.passwordTwo" placeholder="请再次输入新密码" />
				</uni-forms-item>
			</uni-forms>
		</view>
		<view class="flex-center">
			<view class="commonBtn" @click="submit">
				确认修改
			</view>
		</view>
	</view>
</template>

<script>
	import commonHeader from '@/components/header/common.vue'
	export default {
		components: {
			commonHeader
		},
		data() {
			return {
				title: '修改密码',
				rules: {
					newPassword: {
						rules: [{
							required: true,
							errorMessage: '请输入',
						}]
					},
					passwordTwo: {
						rules: [{
							required: true,
							errorMessage: '请输入',
						}]
					},
					code: {
						rules: [{
							required: true,
							errorMessage: '请输入',
						}]
					},
				},
				formData: {
					code: '',
					newPassword: '',
					passwordTwo: '',
				},
			}
		},
		methods: {
			submit() {
				this.$refs.form.validate().then(res => {
					uni.showToast({
						title: '修改成功，请重新登录',
					});
					setTimeout(() => {
						uni.navigateTo({
							//关闭当前页面，跳转到应用内的某个页面。
							url: '/pages/login/index'
						});
					}, 500)
					console.log('表单数据信息：', res);
				}).catch(err => {
					console.log('表单错误信息：', err);
				})
			}
		}
	}
</script>

<style>
	::v-deep .uni-forms-item__label {
		font-size: 18px;
		color: black;
		font-weight: bold;
	}


	.input {
		padding-bottom: 10rpx;
		border-bottom: 1px solid gainsboro;
		height: 80rpx;
	}

	.btn {
		margin-left: 20rpx;
		width: 180rpx;
		height: 70rpx;
		line-height: 70rpx;
		color: white;
		font-weight: bold;
		text-align: center;
		background: #5878FC;
		border-radius: 35rpx;
	}

	.selectBtn {
		margin-left: 20rpx;
		width: 180rpx;
		height: 70rpx;
		line-height: 70rpx;
		color: white;
		font-weight: bold;
		text-align: center;
		background: #5878FC;
		border-radius: 35rpx;
		color: white;
		background: grey;
	}
</style>
