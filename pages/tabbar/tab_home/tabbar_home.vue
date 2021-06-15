<template>
	<u-index-list :scrollTop="scrollTop" :index-list=indexList>
		<view v-for="(item, index) in indexList" :key="index">
			<u-index-anchor :index="item" />

			<view class="list-cell" v-for="ele in data[item]">
				{{ele.name}}
			</view>

		</view>
	</u-index-list>
</template>

<script>
	import {
		data
	} from './data.js'
	export default {
		data() {
			return {
				scrollTop: 0,
				//indexList: ["A", "B", "C", "F", "G", "H", "J", "L", "N", "Q", "S", "T", "X", "Y", "Z"],
				data
			}
		},
		computed: {
			indexList() {
				return data.map(f => {
					return Object.keys(f).pop()
				})
			}
		},
		onPageScroll(e) {
			this.scrollTop = e.scrollTop;
		},
		onLoad() {

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
		color: #323233;
		font-size: 14px;
		line-height: 24px;
		background-color: #fff;
	}
</style>
