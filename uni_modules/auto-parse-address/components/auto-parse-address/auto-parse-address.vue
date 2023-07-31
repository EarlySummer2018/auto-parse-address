<template>
	<view class="auto-box" :class="boxClass">
		<textarea
		v-model="value" 
		class="auto-textarea"
		:class="areaClass"
		:auto-height="autoHeight"
		:placeholder="placeholder" 
		 />
		<text class="auto-btn" :class="btnClass" @click="autoParse()">自动识别</text>
	</view>
</template>
<script>
	import AddressParse from './zh-address-parse.min.js'
	/**
	 * autoParseAddress 自动解析地址
	 * auto-parse-address 自动解析地址
	 * @description 自动解析粘贴过来的地址 本插件是二次开发为uniapp版本，参考来自 [https://github.com/ldwonday/zh-address-parse]
	 * @tutorial 说明文档 https://github.com/EarlySummer2018/auto-parse-address/blob/main/README.md
	 * 
	 * @property {Boolean}			autoHeight		textarea高度自适应, 默认值：true
	 * @property {String}			placeholder		提示文本 默认值：粘贴收货信息
	 * @property {Number|String}	parseType		哪种方式解析，0：正则，1：树查找
	 * @property {Array}			textFilter		预清洗的字段
	 * @property {Number|String}	nameMaxLength	查找最大的中文名字长度，默认值 4
	 * @property {String}			boxClass		容器类名，如果不生效 请在该类名前面加 /deep/
	 * @property {String}			areaClass		textarea 类名，如果不生效 请在该类名前面加 /deep/
	 * @property {String}			btnClass		按钮类名，如果不生效 请在该类名前面加 /deep/
	 * @event {Function}			result			解析之后返回结果方法 result()
	 * @event {Function}			autoParse		点击解析地址
	 * @return {Object}				返回值			{ province: '', name: '', city: '', area: '', detail: '', phone: '', postalCode: '' }
	 * @example
	 * <auto-parse-address boxClass="c-box" @result="result" placeholder="粘贴地址自动解析666"></auto-parse-address>
	 * */
	export default {
		props: {
			autoHeight: {
				type: Boolean,
				default: true
			},
			boxClass: {
				type: String,
				default: ''
			},
			areaClass: {
				type: String,
				default: ''
			},
			btnClass: {
				type: String,
				default: ''
			},
			placeholder: {
				type: String,
				default: '粘贴收货信息'
			},
			parseType: {
				type: [Number, String],
				default: 0
			},
			textFilter: {
				type: Array,
				default() {
					return []
				}
			},
			nameMaxLength: {
				type: [Number, String],
				default: 4
			}
		},
		data() {
			return {
				value: ''
			}
		},
		methods: {
			autoParse() {
				const len = this.value.replace(/\s+/g,"")
				if(len.length===0) return
				const parseResult = AddressParse(this.value, this.parseType,this.textFilter)
				this.$emit('result', parseResult)
			}
		}
	}
</script>
<style lang="scss" scoped>
	.auto-box {
		width: 600upx;
		padding: 30upx 30upx 0upx;
		text-align: right;
		box-sizing: border-box;
		
		.auto-textarea {
			width: 100%;
			text-align: left;
			box-sizing: border-box;
			min-height: 200upx;
			padding: 20upx;
			border-radius: 5upx;
			border: 2upx solid rgb(220, 223, 230);
		}

		.auto-btn {
			display: inline-block;
			padding: 10upx 20upx;
			margin: 20upx 0;
			border: 2upx solid #000;

			&:active {
				background-color: #f3f0f0;
			}
		}
	}
</style>
