<template>
	<div>
		<u-subsection :list="list" :current="current" @change="sectionChange"></u-subsection>
		<u-cell-group title="保定市">
			<u-cell-item icon="setting-fill" v-if="showA" title="河北大学" use-label-slot>
				<view slot="label">
					<label>识别码:4113010075</label>
				</view>
			</u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北农业大学" label="4113010086"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="保定学院" label="4113010096"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北金融学院" label="4113011420"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="中央司法警官学院" label="4113011903"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showA" title="河北科技学院" label="4113013391"></u-cell-item>
			<u-cell-item icon="setting-fill" v-if="showB" title="河北软件职业技术学院" label="4113012352"></u-cell-item>
		</u-cell-group>
	</div>

</template>

<script>
	export default {
		data() {
			return {
				options: {},
				list: [{
						name: '本科'
					},
					{
						name: '专科'
					}
				],
				current: 0
			}
		},
		computed: {
			showA() {
				return this.current == 0
			},
			showB() {
				return this.current == 1
			}
		},
		onLoad(opt) {
			try {
				this.options = JSON.parse(decodeURIComponent(opt.p))

				uni.setNavigationBarTitle({
					title: this.options.name
				})
			} catch (e) {

			}
		},
		methods: {
			sectionChange(index) {
				this.current = index;
			}
		}
	}
</script>

<style scoped lang="scss">
	.u-card-wrap {
		background-color: $u-bg-color;
		padding: 1px;
	}

	.u-body-item {
		font-size: 32rpx;
		color: #333;
		padding: 20rpx 10rpx;
	}

	.u-body-item image {
		width: 120rpx;
		flex: 0 0 120rpx;
		height: 120rpx;
		border-radius: 8rpx;
		margin-left: 12rpx;
	}
</style>
