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
	</view>
</template>

<script>
	import IndexSwiper from '@/components/index/indexSwiper.vue'
	import Recommend from '@/components/recommend/recommend.vue'
	export default {
		data() {
			return {

			}
		},
		components:{
			IndexSwiper,
			Recommend
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
