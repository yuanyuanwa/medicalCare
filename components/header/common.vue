<template>
	<view>
		<view class="header" :style="{background:bgcolor,color:color}">
			<view v-if="hasBack" style="position: absolute;left: 10rpx;" class="iconfont icon-jiantou_qiehuanzuo_o font-32"
				@click="goBack()"></view>
			<text class="font-18">{{title}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			title: {
				type: String,
				default: 'title'
			},
			hasBack: {
				type: Boolean,
				default: false
			},
			bgcolor:{
				type: String,
				default: ''
			},
			color:{
				type: String,
				default: 'black'
			}
			// isBack: {
			// 	type: [Boolean, String],
			// 	default: false
			// },
			// bgImage: {
			// 	type: String,
			// 	default: ''
			// },
		},
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {
			goBack() {
				console.log('返回上一页')
				// uni.navigateBack({
				// 	//关闭当前页面，返回上一页面或多级页面。
				// 	delta: 1
				// });
				history.back()
			}
		}
	}
</script>

<style>
	.header {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 90rpx;
		line-height: 90rpx;
		/* font-weight: bold; */
		/* background-color: rgb(248, 248, 248); */
	}
</style>
