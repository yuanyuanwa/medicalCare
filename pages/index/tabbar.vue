<template>
	<view class="page">
		<view class="">
			<shop v-if="currentBar=='shop'"></shop>
			<chat v-if="currentBar=='chat'"></chat>
			<me v-if="currentBar=='person'"></me>
		</view>
		<view class="box">
			<view class="foot flex-around">
				<view class="p-10" @click="NavChange" data-cur="shop">
					<uni-icons type="shop" size="30" :color="currentBar=='shop'?'#5878FC':''"></uni-icons>
					<view :class="currentBar=='shop'?'select':''">
						订单
					</view>
				</view>
				<view class="p-10" @click="NavChange" data-cur="chat">
					<uni-icons type="chat" size="30" :color="currentBar=='chat'?'#5878FC':''"></uni-icons>
					<view :class="currentBar=='chat'?'select':''">
						消息
					</view>
				</view>
				<view class="p-10" @click="NavChange" data-cur="person">
					<uni-icons type="person" size="30" :color="currentBar=='person'?'#5878FC':''"></uni-icons>
					<view :class="currentBar=='person'?'select':''">
						我的
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import me from "./me.vue"; //我的
	import shop from "./shop.vue"; //我的
	import chat from "./chat.vue"; //我的
	export default {
		components: {
			me,
			chat,
			shop,
		},
		data() {
			return {
				currentBar: 'shop',
			}
		},
		methods: {
				NavChange(e){
					console.log(9999,e.currentTarget.dataset.cur)
					this.currentBar=e.currentTarget.dataset.cur
				}
		}
	}
</script>

<style scoped>
	.page{
		height: 92vh;
		overflow: auto;
	}
	.foot {
		height: 100rpx;
		width: 100%;
		position: fixed;
		bottom: 0;
		background: white;
		z-index: 2;
		box-shadow: 0 -1upx 6upx rgba(0, 0, 0, 0.1);
	}

	.select {
		color: #5878FC;
	}
</style>
