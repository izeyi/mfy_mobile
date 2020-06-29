<template>
	<!-- <cmd-nav-bar iconOne="menu" title="基本" iconTwo="share" iconThree="reload" iconFour="help"></cmd-nav-bar> -->
	<view class="content">
		<mian></mian>
	</view>
</template>

<script>
	import mian from '../../components/index.vue'
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		components:{
			mian
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
