<template>
	<view class="wrap">
		<u-swiper :list="list" height="420" borderRadius="0"></u-swiper>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item1.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item2.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item3.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item4.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item7.jpg" mode="widthFix"></image>
		<!-- <u-gap height="60" bg-color="#ededed"></u-gap> -->
		<image style="width:100%" src="../static/home/item8.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item5.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/home/item6.jpg" mode="widthFix"></image>
		<u-gap height="180" bg-color="#ededed"></u-gap>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						image: '/static/home/banner1.jpeg'
					},
					{
						image: '/static/home/banner2.jpg'
					},
					{
						image: '/static/home/banner3.jpg'
					}
				]
			}
		},
		methods:{
			getData(){
				console.log('首页')
			}
		}
	}
</script>

<style>

.wrap{
	font-size:0 ;
}
</style>
