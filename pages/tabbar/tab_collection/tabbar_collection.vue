<template>
	<view class="content">
		<u-empty :text="noCollectionTxt" mode="favor"></u-empty>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				noCollectionTxt: '您还没有收藏高校,快去收藏吧~'
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
