<template>
	<view class="index">
		<!-- #ifdef MP-WEIXIN -->
		<view class="wx-nav">
			<view class="iconfont icon-sousuo"></view>
			<view class="iconfont icon-dkw_xiaoxi"></view>
		</view>
		<!-- #endif -->
		<Banner></Banner>
		<Icons></Icons>
		<IndexSwiper></IndexSwiper>
		<Recommend></Recommend>
		<!-- cardTitle可以定义不同的名称 -->
		<Card cardTitle='猜你喜欢'></Card>
		<CommodityList></CommodityList>
		<Card cardTitle='热销爆品'></Card>
		<Hot></Hot>
	</view>
</template>

<script>
	import IndexSwiper from '@/components/index/indexSwiper.vue'
	import Recommend from '@/components/recommend/recommend.vue'
	import Card from '@/components/common/Card.vue'
	import Commodity from '@/components/common/Commodity.vue'
	import CommodityList from '@/components/common/CommodityList.vue'
	import Banner from '@/components/index/banner.vue'
	import Icons from '@/components/index/icons.vue'
	import Hot from '@/components/index/hot.vue'
	export default {
		data() {
			return {

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
			Hot
		},
		methods: {

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
</style>
