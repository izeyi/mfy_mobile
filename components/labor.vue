<template>
	<view class="wrap">
		<u-swiper :list="list" height="420" borderRadius="0"></u-swiper>
		<image style="width:100%" src="../static/labor/item1.jpg" mode="widthFix"></image>
		<image style="width:100%" src="../static/labor/item2.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/labor/item3.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/labor/item4.jpg" mode="widthFix"></image>
		<u-gap height="60" bg-color="#ededed"></u-gap>
		<image style="width:100%" src="../static/labor/item5.jpg" mode="widthFix"></image>\
		<u-gap height="180" bg-color="#ededed"></u-gap>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						image: '/static/labor/banner1.jpg',
						title: '蒹葭苍苍，白露为霜。所谓伊人，在水一方'
					},
					{
						image: '/static/labor/banner2.jpg',
						title: '溯洄从之，道阻且长。溯游从之，宛在水中央'
					}
				]
			}
		},
		methods:{
			getData(){
				console.log('帮助')
			}
		}
	}
</script>

<style>
.wrap{
	font-size: 0;
}
</style>
