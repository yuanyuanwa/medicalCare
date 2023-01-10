<template>
	<view>
		<commonHeader :title="title" :hasBack='true'/>
		<view class="p-30">
			<uni-forms :modelValue="formData" label-position="top" :rules="rules" ref="form" :labelWidth='140'>
				<uni-forms-item label="手机号:" name="phone">
					<view class="flex-align-center">
						<!-- <input type="password" style='width:0;height:0;min-height:0' />
						<input type="text" autocomplete="off" style='width:0;height:0;min-height:0' /> -->
						<input class="input" style="flex-grow: 1;" type="text" v-model="formData.phone"
							placeholder="请输入姓名" />
						<view :class="btn" @click="getCode">
							{{btnText}}
						</view>
					</view>
				</uni-forms-item>
				<uni-forms-item label="输入验证码:" name="code">
				<!-- 	<input type="password" style='width:0;height:0;min-height:0' />
					<input type="text" autocomplete="off" style='width:0;height:0;min-height:0' /> -->
					<input class="input" type="text" v-model="formData.code" placeholder="请输入姓名" />
				</uni-forms-item>
				<uni-forms-item label="设置新密码:" name="newPassword">
					<input autocomplete="new-password " class="input" type="password" v-model="formData.newPassword"
						placeholder="请输入新密码" />
				</uni-forms-item>
				<uni-forms-item label="再次输入密码:" name="passwordTwo">
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
				title: '找回密码',
				timer: '',
				btn: 'btn',
				count:'-1',
				formData: {
					phone: '',
					code: '',
					newPassword: '',
					passwordTwo: '',
				},
				rules: {
					phone: {
						rules: [{
								required: true,
								errorMessage: '请输入',
							},
							// {
							// 	minLength: 3,
							// 	maxLength: 5,
							// 	errorMessage: '姓名长度在 {minLength} 到 {maxLength} 个字符',
							// }
						]
					},
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
				}
			}
		},
		 computed: {
		    btnText: function () {
		      return this.count >= 0 ? this.count + 's 后重发' : '获取验证码';
		    },
		  },
		methods: {
			getCode() {
				if (!this.timer) {
					this.count = 60;
					this.btn = 'selectBtn';
					this.timer = setInterval(() => {
						if (this.count > 0 && this.count <= 60) {
							this.count--;
						} else {
							this.count = -1,
							this.btn = 'btn';
							clearInterval(this.timer);
							this.timer = null;
						}
					}, 1000);
				}
			},
			submit(){
				this.$refs.form.validate().then(res => {
					console.log('表单数据信息：', res);
				}).catch(err => {
					console.log('表单错误信息：', err);
				})
			}
		}
	}
</script>

<style scoped>
	::v-deep .uni-forms-item__label {
		font-size: 18upx;
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
