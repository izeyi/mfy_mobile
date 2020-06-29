<template>
	<view class="wrap">
		<u-swiper :list="list" height="420" borderRadius="0"></u-swiper>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/task/item1.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/task/item2.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<view class="experience">
			<u-button type="warning" shape="circle" size="medium" :ripple="true" ripple-bg-color="#909399" @click="ToExperience(2, '/pages/call')">
				<text class="experience_btn">立即咨询体验</text>
			</u-button>
		</view>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/task/item3.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/task/item4.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/task/item5.jpg" mode="widthFix"></image>
		<u-gap height="180" bg-color="#ededed"></u-gap>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						image: '/static/task/banner.jpeg',
						title: '蒹葭苍苍，白露为霜。所谓伊人，在水一方'
					},
					{
						image: '/static/task/banner2.jpeg',
						title: '溯洄从之，道阻且长。溯游从之，宛在水中央'
					},
					{
						image: '/static/task/banners.jpg',
						title: '蒹葭萋萋，白露未晞。所谓伊人，在水之湄'
					}
				]
			}
		},
		inject:['_mainFuncInit'], // 父级传递过来的函数
		methods:{
			getData(){
				console.log('帮助')
			},
			ToExperience(index, Urls) {
				uni.setStorageSync('setStatusIndexFunc', index)
				this._mainFuncInit() // 回调父级函数
				this.active = index
			}
		}
	}
</script>

<style>
.wrap{
	font-size:0 ;
}
.experience{
	width: 100%;
	text-align: center;
	background-color: #ededed;
}
.experience_btn{
	font-weight: 600;
	font-size: 40upx;
	/* line-height:110upx; */
}
.u-size-medium{
	height: 88upx;
}
</style>
