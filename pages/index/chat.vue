<template>
	<view class="box">
		<view class="font-22 p-40">消息列表</view>
		<view class="flex pl-40 pt-20 pb-10 font-18">
			<view class="btn" @click="changeBtn('msg')" :class="curBtn=='msg'?'activeBtn':''">消息</view>
			<view class="btn" @click="changeBtn('person')" :class="curBtn=='person'?'activeBtn':''">患者群</view>
		</view>
		<view class="m-20">
			<uni-easyinput prefixIcon="search" v-model="value" @iconClick="iconClick">
			</uni-easyinput>
		</view>
		<view v-if="curBtn=='msg'">
			<view @click="toPerson()" v-for="(item,index) in 10" class="flex-between"
				style="padding: 14rpx 40rpx;border-bottom: 1px solid gainsboro;">
				<view class="flex-align-center">
					<view class="" style="position: relative;">
						<uni-badge class="uni-badge-left-margin badge" text="1" size='normal' />
						<image class="image" :src="src">
						</image>
					</view>
					<view class="">
						<view><text class="font-bold">李小北</text><text style="color:#808080;">（李小北）</text></view>
						<view style="color: #3E404D;">新年快乐新年快乐</view>
					</view>
				</view>
				<view style="color: #6E707A;">54分钟前</view>
			</view>
		</view>
		<view v-else>
			<view v-for="(item,index) in 10">
				<view @click="changePer(index)" class="flex-between"
					style="padding: 14rpx 40rpx;border-bottom: 1px solid gainsboro;">
					<view class="flex-align-center">
						<view class="" style="position: relative;">
							<image class="image" :src="src">
							</image>
						</view>
						<view class="">
							<view><text class="font-bold">李小北-21位患者-工作室</text></view>
							<view style="color: #3E404D;">您可以联系医生包括他名下所有患者</view>
						</view>
					</view>
					<view style="color: #6E707A;">
						<uni-icons type="bottom" size="30" v-if="curPer!==index"></uni-icons>
						<uni-icons type="top" size="30" v-else></uni-icons>
					</view>
				</view>
				<view class="ml-80 mb-20 per" :class="curPer===index?'activePer':''">
					<view @click="toPerson" v-for="(item,index) in 10" class="flex-between"
						style="padding: 14rpx 0rpx 14rpx 20rpx;border-bottom: 1px solid gainsboro;">
						<view class="flex-align-center">
							<view class="">
								<image class="image" :src="src2">
								</image>
							</view>
								<view><text class="font-bold">李1小北</text><text style="color:#808080;">（李小北）</text></view>
						</view>
						<view style="color: #6E707A;">09/17</view>
					</view>
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				curBtn: 'msg',
				value: '',
				src: '../../static/img/123.jpeg',
				src2: '../../static/img/111.jpeg',
				curPer: '',
			}
		},
		methods: {
			changeBtn(type) {
				this.curBtn = type
			},
			changePer(index) {
				if (this.curPer === index) {
					this.curPer = ''
				} else {
					this.curPer = index
				}
			},
			toPerson(){
				console.log(789)
				uni.navigateTo({
					//关闭当前页面，跳转到应用内的某个页面。
					url: '/pages/chat/person'
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.box {
		height: 95vh;
		width: 100%;
		padding-bottom: 20rpx;
		box-sizing: border-box;
	}

	.btn {
		width: 200rpx;
		height: 80rpx;
		line-height: 80rpx;
		text-align: center;
		border-radius: 40rpx;
	}

	.activeBtn {
		background-color: #5363E3;
		color: white;
	}

	::v-deep .is-input-border {
		border: white !important;
		background-color: #F1F3F9 !important;
		height: 100rpx;
		border-radius: 50rpx;
	}

	.image {
		width: 120rpx;
		height: 120rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}

	.badge {
		position: absolute !important;
		top: 0rpx;
		left: 130rpx;
		z-index: 2;
	}

	.per {
		height: 0rpx;
		border-bottom: 1px solid gainsboro;
		overflow: hidden;
		transition: height 0.5s;
	}

	.activePer {
		height: 300rpx;
		overflow: auto;
	}

	.arrow180 {
		transform: rotateZ(-180deg);
	}
</style>
