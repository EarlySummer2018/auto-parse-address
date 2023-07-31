<template>
	<view class="content">
		<auto-parse-address boxClass="c-box" @result="result" placeholder="粘贴地址自动解析666"></auto-parse-address>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				value: `东省深圳市盐田区东海三街山海四季城F4E，张三，13800138001`
			}
		},
		onLoad() {

		},
		methods: {
			result(res) {
				console.log('res：', res);
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}

	.c-box {
		min-height: 200upx;
	}
</style>