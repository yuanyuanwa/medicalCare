<template>
	<view style="background-color: #5878FC;height: 300rpx">
		<commonHeader :title="title" :hasBack='true' :bgcolor="'#5878FC'" :color="'white'" />
		<view class="docCard">
			<view class="flex-between">
				<view class="flex-align-center">
					<view>
						<image class="image" :src="src">
						</image>
					</view>
					<view>
						<view class="flex-align-center pb-10">
							<view class="font-20 pr-20">
								张医生
							</view>
							<view>
								教授/主任医师
							</view>
						</view>
						<view class="flex-align-center">
							<view class="pr-20">
								西安市中医医院
							</view>
							<view>
								5.0分
							</view>
						</view>
					</view>
				</view>
				<view class="contact">联系TA</view>
			</view>
			<view class="flex-align-center font-14 pt-20">
				<view class="pl-30">24小时回复率99%</view>
				<view class="pl-30">好评率99%</view>
				<view class="pl-30">接待患者120</view>
			</view>
			<view class="line">
			</view>
			<view class="flex-align-center pl-20">
				<view class="tag">图文问诊</view>
				<view class="tag">电话问诊</view>
				<view class="tag" style="color: gainsboro;">视频问诊</view>
			</view>
			<view class="pt-40 pl-20">
				擅长：12313131244312433333333333333
			</view>
		</view>
		<view style="margin: 40rpx 60rpx;">
			<view class="btnBox flex-center">
				<view class="btn" @click="changeBtn('check')" :class="curBtn=='check'?'btnActive':''">问诊订单量：10</view>
				<view class="btn" @click="changeBtn('pill')" :class="curBtn=='pill'?'btnActive':''">药品订单量：8</view>
			</view>
		</view>
		<view class="font-18 font-bold pl-20 pb-20">问诊总收入：483元</view>
		<view v-for="item in 5" v-if="curBtn=='check'">
			<doctor />
		</view>
		<view v-for="item in 5" v-if="curBtn=='pill'">
			药品
			<!-- <doctor /> -->
		</view>
		
		<ball></ball>
		<!-- <my-home></my-home> -->
	</view>
</template>

<script>
	import commonHeader from '@/components/header/common.vue'
	import ball from '../../components/ball/index.vue'
	import doctor from '../index/components/shopDoctor.vue'
	export default {
		components: {
			commonHeader,
			ball,
			doctor
		},
		data() {
			return {
				title: 'XXX医生',
				src: '../../static/img/123.jpeg',
				curBtn: 'check'
			}
		},
		onLoad: function(option) {
			//方式一：接收参数
			console.log(option);

			//方式二：接收参数
			// #ifdef APP-NVUE
			const eventChannel = this.$scope.eventChannel; // 兼容APP-NVUE
			// #endif
			// #ifndef APP-NVUE
			const eventChannel = this.getOpenerEventChannel();
			// #endif
			eventChannel.on('argParams', function(data) {
				console.log(data)
			})
		},
		methods: {
			changeBtn(type) {
				this.curBtn=type
			}
		}
	}
</script>

<style lang="scss" scoped>
	.docCard {
		box-sizing: border-box;
		height: 500rpx;
		width: 100%;
		background-color: #5878FC;
		border-radius: 0px 0px 50rpx 50rpx;
		padding: 20rpx;
		color: white;
	}

	.image {
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}

	.contact {
		background: #5363E3;
		padding: 10rpx;
		border-radius: 15rpx;
	}

	.line {
		width: 100%;
		height: 1px;
		margin: 40rpx 0rpx;
		background-image: linear-gradient(to right, #fff 35%, rgba(255, 255, 255, 0) 0%);
		/* 35%设置虚线点x轴上的长度 */
		background-position: bottom;
		/* top配置上边框位置的虚线 */
		background-size: 34rpx 6rpx;
		/* 第一个参数设置虚线点的间距；第二个参数设置虚线点y轴上的长度 */
		background-repeat: repeat-x;
	}

	.tag {
		background-color: white;
		padding: 10rpx;
		border-radius: 50rpx;
		color: #5363E3;
		font-weight: bold;
		margin-right: 30rpx;
	}

	.btnBox {
		background: #F1F3F9;
		border-radius: 20rpx;
	}

	.btn {
		height: 60rpx;
		line-height: 60rpx;
		margin: 20rpx;
		padding: 10rpx 20rpx;
		border-radius: 16rpx;
	}

	.btnActive {
		background: #5363E3;
		color: white;
	}
</style>
