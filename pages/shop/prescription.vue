<template>
	<view class="box">
		<commonHeader :title="title" :hasBack='true' :bgcolor="'#5878FC'" :color="'white'" />
		<view class="flex-center">
			<view class="card"></view>
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
				title: 'XXX医生'
			}
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.box {
		height: 100vh;
		background: #F0F0FA;
	}

	.card {
		height: 300rpx;
		width: 90%;
		background: #fff;
		margin-top: 40rpx;
		border-radius: 20rpx;
		box-shadow: 0px 2px 12px 0px #E4E4ED;
	}
</style>
