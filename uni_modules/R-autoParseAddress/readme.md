uniapp--自动地址解析，智能识别，支持拼多多，京东复制过来的地址格式，微信小程序和H5亲测可用，其他平台暂无测试
===========

## 封装来源
[ldwonday/zh-address-parse](https://github.com/ldwonday/zh-address-parse)

## Syntax

option可选参数属性列表

|参数名|说明|类型|是否必填|默认值|
|----|----|----|----|----|
|type|解析方式|Number|否|0|
|textFilter|预过滤字段|Array|否|[]|
|nameMaxLength|中文名最大长度|Number|否|4|
|autoHeight|textarea高度自适应|Boolean|否|true|
|placeholder|textarea提示|String|否|粘贴收货信息|
|boxClass|容器类名|String|否|空|
|areaClass|textarea类名|String|否|空|
|btnClass|按钮类名|String|否|空|

类型如果设置不生效 请在该类名前面加 /deep/
## Usage
>[从uniapp插件市场导入](https://ext.dcloud.net.cn/)
```html
<template>
	<view class="content">
		<auto-parse-address boxClass="c-box" @result="result"></auto-parse-address>
	</view>
</template>
```

```js
import AddressParse from '../components/zh-address-parse.vue' //路径修改为自己的实际路径
export default {
		components: {
			'auto-parse-address': autoParseAddress
		},
	}
```

## 备注
> 您的支持是我前进的动力，更好的支持开源事业！~
> 
</a>
