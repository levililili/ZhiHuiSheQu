<template>
	<view class="content">
		<text>所有平台都可见的组件：{{title}}</text>
		<!-- #ifdef H5 -->
		<text>只有H5可见的组件1</text>
		<text>只有H5可见的组件2</text>
		<!-- #endif -->

		<!-- #ifdef APP -->
		<text>只有App可见的组件1</text>
		<text>只有App可见的组件2</text>
		<text>只有App可见的组件3</text>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() { // 类似mounted生命周期
			// 生命周期方法： 组件挂载时
			// #ifdef H5
			this.title = '这是H5'
			// #endif
			// #ifdef APP
			this.title = '这是APP'
			// #endif
		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		/* #ifdef H5 */
		color: pink;
		/* #endif */
		/* #ifdef APP */
		color: blue;
		/* #endif */
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
</style>
