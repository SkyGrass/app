<template>
	<u-index-list :scrollTop="scrollTop" :index-list="indexList">
		<view v-for="(item, index) in list" :key="index">
			<u-index-anchor :index="item.letter" />
			<view class="list-cell u-border-bottom" v-for="(ele, index)
			 in item.list" :key="index" @click="choose(ele)">
				{{ele.name}}
			</view>
		</view>
	</u-index-list>
</template>

<script>
	import {
		data
	} from "./data.js";

	export default {
		data() {
			return {
				scrollTop: 0,
				list: data
			}
		},
		onPageScroll(e) {
			this.scrollTop = e.scrollTop;
		},
		methods: {
			choose(e) {
				uni.navigateTo({
					url: `/pages/university/list?p=${encodeURIComponent(JSON.stringify(e))}`,
				})
			}
		},
		computed: {
			indexList() {
				return data.map(val => {
					return val.letter
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.list-cell {
		display: flex;
		box-sizing: border-box;
		width: 100%;
		padding: 10px 24rpx;
		overflow: hidden;
		color: $u-content-color;
		font-size: 14px;
		line-height: 24px;
		background-color: #fff;
	}
</style>
