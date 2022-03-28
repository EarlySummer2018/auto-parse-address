<template>
	<view class="content">
		<auto-parse-address boxClass="c-box" @result="result"></auto-parse-address>
	</view>
</template>

<script>
	import autoParseAddress from '../../uni_modules/R-autoParseAddress/components/R-autoParseAddress/R-autoParseAddress.vue'
	export default {
		components: {
			'auto-parse-address': autoParseAddress
		},
		data() {
			return {
				value: `收货人: 黄祥瑞
手机号码: 18344050796
所在地区: 广东省广州市番禺区大石街道
详细地址: 广州番禺大山村湾低坊前街15号店`
			}
		},
		onLoad() {

		},
		methods: {
			result(obj) {
				console.log('obj', obj);
			}
		}
	}
</script>

<style>
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
