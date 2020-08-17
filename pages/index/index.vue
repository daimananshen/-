<template>
	<view class="index">
		<!-- #ifdef MP-WEIXIN -->
		<view class="wx-nav">
			<view class="iconfont icon-sousuo"></view>
			<view class="iconfont icon-dkw_xiaoxi"></view>
		</view>
		<!-- #endif -->
		<IndexSwiper></IndexSwiper>
		<Recommend></Recommend>
		<!-- cardTitle可以定义不同的名称 -->
		<Card cardTitle='猜你喜欢'></Card>
		<CommodityList></CommodityList>
	</view>
</template>

<script>
	import IndexSwiper from '@/components/index/indexSwiper.vue'
	import Recommend from '@/components/recommend/recommend.vue'
	import Card from '@/components/common/Card.vue'
	import Commodity from '@/components/common/Commodity.vue'
	import CommodityList from '@/components/common/CommodityList.vue'
	export default {
		data() {
			return {

			}
		},
		components:{
			IndexSwiper,
			Recommend,
			Card,
			Commodity,
			CommodityList
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
