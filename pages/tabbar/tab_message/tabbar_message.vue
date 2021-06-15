<template>
	<view class="content">
		<u-empty :text="noMsgTxt" mode="message"></u-empty>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				noMsgTxt: '没有新消息~'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
		margin-top: 200upx;
	}
</style>
