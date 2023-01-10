<template>
	<view class="box">
		<view class="content" style="height: 50vh;">
			<view>
				<commonHeader :title="title" :hasBack='false' :bgcolor="'#5878FC'" :color="'white'" />
				<!-- <view class="font-22 text-center p-30">订单数据</view> -->
				<view class="flex-left pr-40 p-40">
					<view @click="tabChange" data-cur='check' class="tab" style="border-radius: 5px 0px 0px 5px;"
						:class="curTab=='check'?'selectTab':''">
						问诊
					</view>
					<view @click="tabChange" data-cur='pill' class="tab" style="border-radius: 0px 5px 5px 0px;"
						:class="curTab=='pill'?'selectTab':''">
						药品
					</view>
				</view>
			</view>

			<view class="flex-center" style="flex-grow: 1;">
				<view class="">
					<view class="font-20 text-center pb-30">总金额（元）</view>
					<view class="text-center font-bold pb-30" style="font-size: 120upx;">98.66</view>
					<view class="">
						<view class="">
							<view v-if="curTab=='check'" class="font-20 text-center ">问诊单量：17单</view>
							<view v-if="curTab=='pill'" class="font-20 text-center ">药品单量：99单</view>
						</view>
					</view>
				</view>
			</view>

			<tabMenu class='pb-20'></tabMenu>
		</view>
		<view class="order pt-40 p-20 ">
			<view v-for="item in 5" @click='toDoctor' v-if="curTab=='check'">
				<doctor />
			</view>
			<view v-for="item in 5" v-if="curTab=='pill'">
				<pill></pill>
			</view>
		</view>
	</view>
</template>

<script>
	import tabMenu from '../../components/tabMenu/index.vue'
	import doctor from './components/shopDoctor.vue'
	import pill from './components/shopPill.vue'
	import commonHeader from '@/components/header/common.vue'
	export default {
		components: {
			tabMenu,
			doctor,
			commonHeader,
			pill,
		},
		data() {
			return {
				curTab: 'check',
				title: '订单数据'
			}
		},
		methods: {
			tabChange(e) {
				console.log(9999, e.currentTarget.dataset.cur)
				this.curTab = e.currentTarget.dataset.cur
			},
			toDoctor() {
				console.log(789789789)
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
	.box {
		background: #5878FC;
		height: 95vh;
		color: white;
	}

	.tab {
		height: 70rpx;
		border: 2px solid white;
		line-height: 70rpx;
		padding: 0px 40rpx;
		font-size: 18px;
		font-weight: bold;
	}

	.selectTab {
		background: white;
		color: #5878FC;
	}

	.order {
		height: 50vh;
		position: fixed;
		bottom: 0px;
		background: white;
		width: 100%;
		border-radius: 60rpx 60rpx 0rpx 0rpx;
		overflow-y: auto;
		color: black;
		box-sizing: border-box;
	}

	.foot {
		position: fixed;
		top: 46vh;
		width: 100%;
	}

	.content {
		display: flex;
		justify-content: space-between;
		flex-direction: column;
	}
</style>
