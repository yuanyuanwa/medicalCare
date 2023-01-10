<template>
	<view>
		<movable-area class="movable-area">
			<movable-view class="movable-view" :x="x" :y="y" direction="all">
				<image class="image" src="@/static/img/123.jpeg"></image>
			</movable-view>
		</movable-area>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: '@/static/img/123.jpeg',
				x: 320, //x坐标
				y: 520, //y坐标
			}
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	$all_width: 96rpx;
	$all_height:96rpx;

	.movable-area {
		height: 100vh;
		width: 750rpx;
		top: 0;
		position: fixed;
		pointer-events: none; //此处要加，鼠标事件可以渗透

		.movable-view {
			width: $all_width;
			height: $all_height;
			pointer-events: auto; //恢复鼠标事件

			image {
				width: $all_width;
				height: $all_height;
			}
		}
	}
	.image {
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		margin: 0rpx 30rpx;
	}
</style>
