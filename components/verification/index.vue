<template>
	<view>
		<view class="register">
			<view class="canvas-img-code" @click="refresh()">
				<canvas :style="{ width: width + 'px', height: height + 'px' }" canvas-id="imgcanvas"
					@error="canvasIdErrorCallback"></canvas>
			</view>
		</view>
	</view>
</template>

<script>
	var _this;

	export default {
		data() {
			return {
				verCode: "", // 验证码
				width: 120,
				height: 35,
			};
		},
		components: {},

		// 组件里用mounted， 页面里面用onshow
		mounted() {
			_this = this;
			setTimeout(function() {
				_this.init();
			}, 1000);
		},
		methods: {
			// 初始化验证码
			init: function() {
				console.log('start');
				var context = uni.createCanvasContext('imgcanvas', this);
				var w = this.width;
				var h = this.height;
				context.setFillStyle("white");
				context.setLineWidth(5);
				context.fillRect(0, 0, w, h);
				var pool = [
					"A",
					'B',
					"C",
					'D',
					"E",
					'F',
					"G",
					'H',
					"I",
					'J',
					'K',
					"L",
					'I',
					"M",
					'N',
					"O",
					'P',
					"Q",
					'R',
					"S",
					'T',
					"U",
					'V',
					"W",
					'S',
					"Y",
					"Z",
					'1',
					"2",
					'3',
					"4",
					'5',
					"6",
					"7",
					'8',
					"9",
					"0",
				];
				var str = "";
				for (var i = 0; i < 4; i++) {
					var c = pool[this.rn(0, pool.length - 1)];
					var deg = this.rn(-30, 30);
					context.setFontSize(18);
					context.setTextBaseline("top");
					context.setFillStyle(this.rc(80, 150));
					context.save();
					context.translate(30 * i + 15, parseInt(h / 1.5));
					context.rotate((deg * Math.PI) / 180);
					context.fillText(c, -15 + 5, -15);
					context.restore();
					str += c;
				}
				uni.setStorage({
					key: 'imgcode',
					data: str,
				});
				for (var i = 0; i < 40; i++) {
					context.beginPath();
					context.arc(this.rn(0, w), this.rn(0, h), 1, 0, 2 * Math.PI);
					context.closePath();
					context.setFillStyle(this.rc(150, 200));
					context.fill();
				}
				context.draw();
				console.log('end',str);
				this.$emit('getData',str)
			},
			rc: function(min, max) {
				var r = this.rn(min, max);
				var g = this.rn(min, max);
				var b = this.rn(min, max);
				return "rgb(" + r + "," + g + "," + b + ")";
			},
			rn: function(max, min) {
				return parseInt(Math.random() * (max - min)) + min;
			},
			refresh: function() {
				this.init();
			},
			canvasIdErrorCallback: function(e) {
				console.error(e.detail.errMsg);
			},
		},
	};
</script>

<style scoped></style>
