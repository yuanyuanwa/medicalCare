<template>
	<view class="shopOrderBox flex-column-between mb-20">
		<view class="flex-between p-10 m-20 font-18 shopOrderTitle">
			<view class="">
				订单号：121321
			</view>
			<view class="">
				已完成
			</view>
		</view>
		<view class="">
			2222
		</view>
		<view class=" p-10 m-20 font-18 shopOrderFoot" >
			支付金额：12378312
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style scoped>
	.shopOrderBox {
		height: 210px;
		background: #F1F3F9;
		border-radius: 10px;

	}
	.shopOrderTitle{
		color:#888989;
		border-bottom: 1px solid gainsboro;
	}
	.shopOrderFoot{
		color: #FD9C3B;
		border-top: 1px dashed gainsboro;
		text-align: right;
		font-weight: bold;
	}
</style>
