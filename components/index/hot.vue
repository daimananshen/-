<template>
	<view class='hot'>
		
		<Commodity :dataList='hotList' itemW='250rpx' bigH='220rpx'></Commodity>
		
	</view>
</template>

<script>
import Commodity from '../common/Commodity.vue'
export default{
	data () {
		return {
			hotList:[
				{
					id:1,
					imgUrl:"../../static/img/hot1.jpg",
					name:"回力帆布鞋男低帮夏季男鞋韩版潮流百搭透气布鞋休闲潮鞋子男板鞋",
					pprice:"299",
					oprice:"659",
					discount:"5.2"
				},
				{
					id:2,
					imgUrl:"../../static/img/hot2.jpg",
					name:"KAPPA/卡帕 专柜男鞋女鞋春秋款情侣复古经典透气跑步鞋K0725MM31",
					pprice:"299",
					oprice:"659",
					discount:"5.2"
				},
				{
					id:3,
					imgUrl:"../../static/img/hot3.jpg",
					name:"KAPPA/卡帕 专柜男鞋女鞋春秋款情侣复古经典透气跑步鞋K0725MM31",
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
