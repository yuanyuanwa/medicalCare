<template>
	<view>
		<view class="flex-around pb-40 tab-box">
			<!-- 	<view class="activeBar p-10">
				今日
			</view>
			<view class="p-10">
				本周
			</view>
			<view class="p-10">
				本月
			</view>
			<view class="p-10">
				筛选日期
				<uni-icons type="bottom" size="20" color="white"></uni-icons>
			</view> -->
			<view class="tab-item" @click="testTabClick(index)" :class="tabIndex == index?'active':''"
				v-for="(item,index) in tabList" :key="index">
				{{item.name}}
				<uni-icons v-if="item.name=='筛选日期'" type="bottom" size="20" color="white"></uni-icons>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabIndex: 0,
				tabList: [{
					name: "今日"
				}, {
					name: "本周"
				}, {
					name: "本月"
				}, {
					name: "筛选日期"
				}]
			}
		},
		methods: {
testTabClick(index) {
				console.log(index)
				this.tabIndex = index
			}
		}
	}
</script>

<style lang="scss" scoped>
	.tab-box{
			display: flex;
			.tab-item{
				flex-shrink: 0;
				padding: 24rpx;
				position: relative;
				&::after{
					transition: all 0.2s linear;
					transform: translateX(-50%) scaleX(0);
					content: '';
					width: 60%;
					position: absolute;
					left: 50%;
					bottom: 20rpx;
					border-bottom: 6rpx solid white;
					border-radius: 4rpx;
				}
				&.active{
					&::after{
						transform: translateX(-50%) scaleX(1);					
					}
				}
			}
		}
</style>
