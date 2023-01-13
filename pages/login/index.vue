<template>
	<view class="bg flex-align-center">
		<view style="flex-grow: 1;">
			<view class="font-36 p-10 pb-50" style="text-align: left;">
				登录
			</view>
			<view class="pl-30 pr-30 flex-center">
				<uni-forms :modelValue="formData" :rules="rules" ref="form">
					<uni-forms-item label="姓名:" name="name">
						<uni-easyinput style="width: 500rpx;" type="text" v-model="formData.name" placeholder="请输入姓名" />
					</uni-forms-item>
					<uni-forms-item label="年龄:" name="age">
						<uni-easyinput style="width: 500rpx;" type="password" v-model="formData.age"
							placeholder="请输入年龄" />
						<!-- <input type="text" v-model="formData.age" placeholder="请输入年龄" /> -->
					</uni-forms-item>
					<uni-forms-item label="验证码:" name="code">
						<view class="flex">
							<uni-easyinput  style="width: 300rpx;" type="text" v-model="formData.code"
								placeholder="请输入验证码" />
								<view class='ml-10' style="background: white;">
									<verification @getData='getData'></verification>
								</view>
						</view>
					</uni-forms-item>
				</uni-forms>
			</view>
			<view style="color: #5878FC;font-size: 16px; text-align: right;" class="pr-30" @click="findPassword">忘记密码</view>

			<view class="flex-center pt-30">
				<view @click="goregirect" class="loginBtn">登录</view>
			</view>
			<view class="flex-center pt-10" :class="isshake?'a-shake':''">
				<label style="font-size: 14upx;" @click="changeRadio"><radio value="r2"  :checked="checked" v-model="isAdmin" style="transform:scale(0.7);"/>我已阅读<text style="color:#5878FC;">《隐私政策》</text>和<text style="color:#5878FC;">《用户使用协议》</text></label>
			</view>
		</view>
	</view>
</template>

<script>
	import verification from "@/components/verification/index.vue"
	export default {
		components: {
			verification
		},
		data() {
			return {
				formData: {
					name: '',
					age: '',
					code: '',
				},
				isshake:false,
				checked:false,
				isAdmin:'',
				rules: {
					// 对name字段进行必填验证
					name: {
						rules: [{
								required: true,
								errorMessage: '请输入姓名',
							},
							{
								minLength: 3,
								maxLength: 5,
								errorMessage: '姓名长度在 {minLength} 到 {maxLength} 个字符',
							}
						]
					},
					age: {
						rules: [{
							required: true,
							errorMessage: '请输入密码',
						}]
					},
					code: {
						rules: [{
							required: true,
							errorMessage: '请输入验证码',
						}]
					},
				}
			}
		},
		methods: {
			goregirect() {		
				this.isshake=!this.checked
				setTimeout(()=>{
					this.isshake=false
				},1000)
				this.$refs.form.validate().then(res => {
					if(!this.checked){
						return
					}
					console.log('表单数据信息：', res);
					uni.showToast({
						title: '登录成功',
					});					
					setTimeout(()=>{
						uni.navigateTo({
							//关闭当前页面，跳转到应用内的某个页面。
							url: '/pages/index/tabbar'
						});
					},500)
					
				}).catch(err => {
					console.log('表单错误信息：', err);
				})
			},
				
			getData(data){
				console.log(999,data)
			},
			findPassword(){
				uni.navigateTo({
					//关闭当前页面，跳转到应用内的某个页面。
					url: '/pages/login/findPassword'
				});
			},
			changeRadio(){
				this.checked=!this.checked
			}
		}
	}
</script>

<style scoped>
	.bg {
		height: 100vh;
		background-color: #fcfcfc;
		background-image: linear-gradient(180deg, #fcfcfc 0%, #dfe8fe 100%);
	}

	.login {
		padding: 10px;
	}


	.loginBtn {
		width: 500rpx;
		height: 70rpx;
		line-height: 70rpx;
		color: white;
		font-weight: bold;
		text-align: center;
		background: #5878FC;
		border-radius: 16rpx;
	}

	::v-deep .uni-forms-item__label {
		font-size: 16upx;
	}
</style>
