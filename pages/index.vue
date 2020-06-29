<template>
	<view class="mainVieW">
		<cmd-nav-bar leftTitle="魔方云" iconTwo="menu"  @iconTwo="showDrawer('showRight')"></cmd-nav-bar>
		<uni-drawer ref="showRight" mode="right" @change="change($event,'showRight')">
			<!-- #ifndef MP-BAIDU || MP-ALIPAY || MP-TOUTIAO -->
			<uni-list>
				<uni-list-item title="首页" @click="ToExperience(0,'showRight')"/>
				<uni-list-item title="云创客" @click="ToExperience(1,'showRight')"/>
				<uni-list-item title="用工社" @click="ToExperience(3,'showRight')"/>
				<uni-list-item title="立即体验" @click="ToExperience(2,'showRight')"/>
				<uni-list-item title="关于我们" @click="ToExperience(4,'showRight')"/>
			</uni-list>
			<!-- #endif -->
			<!-- #ifdef MP-BAIDU || MP-ALIPAY || MP-TOUTIAO -->
			<view class="uni-list">
				<uni-list-item title="首页" @click="ToExperience(0,'showRight')"/>
				<uni-list-item title="云创客" @click="ToExperience(1,'showRight')"/>
				<uni-list-item title="用工社" @click="ToExperience(3,'showRight')"/>
				<uni-list-item title="立即体验" @click="ToExperience(2,'showRight')"/>
				<uni-list-item title="关于我们" @click="ToExperience(4,'showRight')"/>
			</view>
			<!-- #endif -->
			<view class="close">
				<view class="word-btn" hover-class="word-btn--hover" :hover-start-time="20" :hover-stay-time="70" @click="ToExperience(2,'showRight')">
					<text class="word-btn-white">即刻体验</text>
				</view>
			</view>
		</uni-drawer>

		<!-- 主站 -->
		<HOMES ref='Home' v-if='active==0'></HOMES> 
		<MAPS ref='maps' v-if='active==1'></MAPS>
		<CALL ref='call' v-if='active==2'></CALL>
		<HELPS ref='htlp' v-if='active==3'></HELPS>
		<USERCENTER ref='userCent' v-if='active==4'></USERCENTER>
		
		<tab-bar class="fixs" ref='commentTabbat' :actives='active'></tab-bar>
	</view>
</template>
<script>
	
import HOMES from '../components/home.vue'
import USERCENTER from '../components/about.vue'
import HELPS from '../components/labor.vue'
import MAPS from '../components/task.vue'
import CALL from '../components/call.vue'

/**
 * @name 次功能适用于APP  H5  小程序
 * 小程序不需要 import 导入 tabbar
 * APP 端如需使用自定义tabbar  需要单独 import 导包形式 进行components 注入组件 
 * 该组件样式BUG问题已全部修复可以直接使用
 * */ 
 
import tabBar from '../components/tabbar.vue'
import cmdNavBar from "@/components/cmd-nav-bar/cmd-nav-bar.vue"
import uniDrawer from "@/components/uni-drawer/uni-drawer.vue"

export default{
	name:'mains',
	data(){
		return{
			active: Number || 0,
			showRight: false,
		}
	},
	components:{
		HOMES,
		USERCENTER,
		HELPS,
		MAPS,
		tabBar,
		cmdNavBar,
		uniDrawer,
		CALL
	},
	onLoad() {
		let temp = uni.getStorageSync('setStatusIndexFunc') || 0
		uni.setStorageSync('setStatusIndexFunc', temp)
		this.active = temp
		this.$nextTick(()=>{
			this.$refs.commentTabbat.getSetting(temp)
			this._initData();
		})
	},
	provide(){
		return {
			_mainFuncInit: this._mainFuncInit
		}
	},
	methods:{
		// 打开窗口
		showDrawer(e) {
			this.$refs[e].open()
		},
		// 关闭窗口
		closeDrawer(e) {
			this.$refs[e].close()
		},
		// 抽屉状态发生变化触发
		change(e, type) {
			console.log((type === 'showLeft' ? '左窗口' : '右窗口') + (e ? '打开' : '关闭'));
			this[type] = e
		},
		ToExperience(_i,e){
			this.closeDrawer(e);
			this.active = _i
		},
		/**
		 * @name 公共点击函数
		 * */
		_mainFuncInit(){
			this.active = uni.getStorageSync('setStatusIndexFunc') || 0
			console.log(this.active)
			if(this.tempActive == this.active && this.active != 4){ return }
			this.$nextTick(()=>{
				switch(this.active){
					case 0: 
						uni.setStorageSync('setStatusIndexFunc', 0)
						this.$refs.Home.getData(); 
						break;
					case 1: 
						uni.setStorageSync('setStatusIndexFunc', 1)
						this.$refs.maps.getData();
						break;
					case 2: 
						uni.setStorageSync('setStatusIndexFunc', 2)
						this.$refs.call.getData();
						break;
					case 3:
						uni.setStorageSync('setStatusIndexFunc', 3)
						this.$refs.htlp.getData(); 
						break;
					case 4:
						uni.setStorageSync('setStatusIndexFunc', 4)
						this.$refs.userCent.getData(); 
						break;
				}
			})
			this.tempActive = this.active
		},
		/**
		 * @name 首页数据初始化 
		 * */
		_initData(){
			this._mainFuncInit();
		},
		_iconTwo(){
			console.log('123')
		}
	}
}
</script>
<style scoped>
	
.body{
	/*距离顶部范围应该在88-95范围内*/
	padding-top: 90upx;
	top: var(--status-bar-height);
	
}

.fixs{
	position: fixed;
	z-index:100;
}
.word-btn-white {
	font-size: 18px;
	color: #FFFFFF;
}

.word-btn {
	/* #ifndef APP-NVUE */
	display: flex;
	/* #endif */
	flex-direction: row;
	align-items: center;
	justify-content: center;
	border-radius: 6px;
	height: 48px;
	margin: 15px;
	background-color: #007AFF;
}

.word-btn--hover {
	background-color: #4ca2ff;
}
</style>
