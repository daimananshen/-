<template>
	<view class="index">
		<!-- #ifdef MP-WEIXIN -->
		<view class="wx-nav">
			<view class="iconfont icon-sousuo"></view>
			<view class="iconfont icon-dkw_xiaoxi"></view>
		</view>
		<!-- #endif -->
		<scroll-view scroll-x="true" class='scroll-content' :scroll-into-view='scrollIntoIndex'>
			<view class='scroll-item' v-for='(item,index) in topBar' :key='index' @tap='changeTab(index)'>
				<text :class='topBarIndex===index? "f-active-color":"f-color"'>{{item.name}}</text>
			</view>
		</scroll-view>
		<swiper @change='onChangeTab' :current="topBarIndex" :style="'height:'+clentHeight+'px;'">
			<swiper-item v-for='(item,index) in newTopBar' :key='index'>
				<view class='home-data'>
					<block v-for='(k,i) in item.data' :key='i'>
						<template v-if='k.type==="recommendList"'>
							<Recommend :dataList='k.data'></Recommend>
							<Card cardTitle='猜你喜欢'></Card>
						</template>
						<CommodityList v-if='k.type==="commodityList"' :dataList='k.data'></CommodityList>
					</block>
				</view>
			</swiper-item>
		</swiper>

		<!-- <Banner></Banner> -->
		<!-- <Icons></Icons> -->
		<!-- <IndexSwiper></IndexSwiper> -->
		<Recommend></Recommend>
		<!-- cardTitle可以定义不同的名称 -->
		<Card cardTitle='猜你喜欢'></Card>
		<CommodityList></CommodityList>
		<Card cardTitle='热销爆品'></Card>
		<Hot></Hot>
		<Card cardTitle='推荐商铺'></Card>
		<Shop></Shop>
		<Card cardTitle='为您推荐'></Card>
		<CommodityList></CommodityList>
	</view>
</template>

<script>
	import IndexSwiper from '@/components/index/IndexSwiper.vue'
	import Recommend from '@/components/recommend/Recommend.vue'
	import Card from '@/components/common/Card.vue'
	import Commodity from '@/components/common/Commodity.vue'
	import CommodityList from '@/components/common/CommodityList.vue'
	import Banner from '@/components/index/Banner.vue'
	import Icons from '@/components/index/Icons.vue'
	import Hot from '@/components/index/Hot.vue'
	import Shop from '@/components/index/Shop.vue'
	export default {
		data() {
			return {
				//选中的索引
				topBarIndex: 0,
				//顶栏跟随的索引id值
				scrollIntoIndex: 'top0',
				//顶部滑动导航数据
				//内容块的高度值
				clentHeight: 0,
				//顶部导航栏数据
				topBar: [],
				//承载内容数据
				newTopBar: []
			}
		},
		components: {
			IndexSwiper,
			Recommend,
			Card,
			Commodity,
			CommodityList,
			Banner,
			Icons,
			Hot,
			Shop
		},
		onLoad() {
			this.__init();
		},
		onReady() {

			let view = uni.createSelectorQuery().select(".home-data");
			view.boundingClientRect(data => {
				this.clentHeight = 2000;
				// this.clentHeight = data.height;
			}).exec();

		},
		methods: {
			__init() {
				uni.request({
					url: "http://192.168.1.9:3000/api/index_list/data",
					success: (res) => {
						let data = res.data.data;
						this.topBar = data.topBar;
						this.newTopBar = this.initData(data);
					}
				})
			},
			initData(res) {
				let arr = [];
				// 顶部导航栏，长度为7
				for (let i = 0; i < this.topBar.length; i++) {
					let obj = {
						data: []
					}
					//获取首次数据
					if (i == 0) {
						obj.data = res.data;
					}
					arr.push(obj)
				}
				return arr;
			},
			changeTab(index) {
				if (this.topBarIndex === index) {
					return;
				}
				this.topBarIndex = index;
				this.scrollIntoIndex = 'top' + index;
			},
			onChangeTab(e) {
				this.changeTab(e.detail.current);
			}
		}
	}
</script>

<style scoped>
	.wx-nav {
		width: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.scroll-content {
		width: 100%;
		height: 80rpx;
		white-space: nowrap;
	}

	.scroll-item {
		display: inline-block;
		padding: 10rpx 30rpx;
		font-size: 32rpx;
	}

	.f-active-color {
		padding: 10rpx 0;
		border-bottom: 6rpx solid #49BDFB;
	}
</style>
