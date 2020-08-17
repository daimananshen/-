<template>
	<view class='commodity-list'>
		
		<!-- 商品列表组件 -->
		<Commodity :dataList='commodityList'></Commodity>
		
	</view>
</template>

<script>
import Commodity from './Commodity.vue'
export default {
	data () {
		return {
			commodityList:[
				{
					id:1,
					imgUrl:"../../static/img/commodity1.jpg",
					name:"2020年秋季新款韩版原宿慵懒风上衣宽松",
					pprice:"299",
					oprice:"659",
					discount:"5.2"
				},
				{
					id:2,
					imgUrl:"../../static/img/commodity2.jpg",
					name:"2020年秋季新款韩版原宿慵懒风上衣宽松",
					pprice:"299",
					oprice:"659",
					discount:"5.2"
				},
				{
					id:3,
					imgUrl:"../../static/img/commodity3.jpg",
					name:"2020年秋季新款韩版原宿慵懒风上衣宽松",
					pprice:"299",
					oprice:"659",
					discount:"5.2"
				},
				{
					id:4,
					imgUrl:"../../static/img/commodity4.jpg",
					name:"大码女装2020夏季新款胖妹妹收腰显瘦名媛连",
					pprice:"299",
					oprice:"659",
					discount:"5.2"
				}
			]
		}
	},
	components:{
		Commodity
	}
}
</script>

<style>
</style>
