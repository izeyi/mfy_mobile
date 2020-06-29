<template>
	<view class="csll_bady">
		<uni-card>
			<u-cell-group>
				<u-field v-model="comName" label="公司名称" placeholder="请填写公司名称"></u-field>
				<u-field v-model="nikeName" label="联系人" placeholder="请填写您的姓名"></u-field>
				<u-field v-model="phone" label="手机号" placeholder="请填写您的电话号码"></u-field>
			</u-cell-group>
			<u-button @click="submit" shape="circle" type="warning">立即体验</u-button>
		</uni-card>
	</view>
</template>

<script>
	import uniCard from '@/components/uni-card/uni-card.vue'
	export default {
		components: {uniCard},
		data() {
			return {
				comName: '',
				nikeName: '',
				phone:''
			}
		},
		methods: {
			getData(){
				console.log('体验')
			},
			submit() {
				this.$refs.upload();
			},
            onInput(e) {  
                this.$emit('input', e.detail.value)  
            }
			
		}
	}
</script>

<style>
.csll_bady{
	background-color: #F1F1F1;
	width: 100%;
	height: 100%;
	padding: 24upx;
    padding: 1upx;
    box-sizing: border-box;
}
</style>
