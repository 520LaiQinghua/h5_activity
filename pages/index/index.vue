<template>
	<view class="content">
		<search/>
	 <view>
	 	<swiper :list="swiperList"/>
		<grid :list="gridList"/>
	 </view>
	 <view class="themth" v-for="(item,index) in topicList" :key="index">
	 	<activityName :title="item.title"  :list="item.goodsList"/>
		<specialName/>
		<topicName1 :list="item.goodsList"/>
		<topicName2 :list="item.goodsList" :list2="navList" ref="navc" :navIndex="navIndex" @goodClassifyClick="goodClassifyClick"/>
	 </view>
	</view>
</template>

<script>
   import search from "@/components/index/header.vue"
   import swiper from "@/components/index/swiper.vue"
   import grid from '@/components/index/grid.vue'
   import activityName from "@/components/index/activityName.vue"
   import specialName from "@/components/index/specialName.vue"
   import topicName1 from '@/components/index/topicName1.vue'
   import topicName2 from '@/components/index/topicName2.vue'
	export default {
		components:{
			search,
			swiper,
			grid,
			activityName,
			specialName,
			topicName1,
			topicName2
		},
		data() {
			return {
				navIndex:0,
				"navList":[
					{
						name:'商城严选'
					},
					{
						name:'家居生活'
					},
					{
						name:'食品酒水'
					},
					{
						name:'家用电器'
					},
					{
						name:'商城严选'
					},
					{
						name:'商城严选'
					},
				],
				"swiperList":[
					{
						imageUrl:'http://pic.mercht.ficea.cn//upload/20200215/15201543759dba.jpg?imageslim'
					},
					{
						imageUrl:'http://pic.mercht.ficea.cn//upload/20200116/143946919b74b9.jpg?imageslim'
					},
					{
						imageUrl:'http://pic.mercht.ficea.cn//upload/20200116/1447533978d441.gif?imageslim'
					}
				],
				"gridList": [
				    {
				      "id": 10,
				      "name": "美妆馆",
				      "url": "/pages/good/active-list?id=37",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20200224/101811912813cd.jpg?imageslim",
				      "sort_order": 2
				    },
				    {
				      "id": 9,
				      "name": "美食馆",
				      "url": "/pages/good/active-list?id=29",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191210/141144517b8cb3.jpg?imageslim",
				      "sort_order": 3
				    },
				    {
				      "id": 6,
				      "name": "家电馆",
				      "url": "/pages/good/active-list?id=30",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191219/1750251599c175.jpg?imageslim",
				      "sort_order": 4
				    },
				    {
				      "id": 7,
				      "name": "家居馆",
				      "url": "/pages/good/active-list?id=28",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191210/1411445043c539.jpg?imageslim",
				      "sort_order": 5
				    },
				    {
				      "id": 8,
				      "name": "箱包馆",
				      "url": "/pages/good/active-list?id=38",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191210/14114451365518.jpg?imageslim",
				      "sort_order": 6
				    },
				    {
				      "id": 2,
				      "name": "服饰馆",
				      "url": "/pages/good/classify-list?id=10500000",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191210/1411445135df95.jpg?imageslim",
				      "sort_order": 7
				    },
				    {
				      "id": 4,
				      "name": "母婴馆",
				      "url": "/pages/good/active-list?id=32",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191210/14114451945396.jpg?imageslim",
				      "sort_order": 8
				    },
				    {
				      "id": 5,
				      "name": "数码馆",
				      "url": "/pages/good/classify-list?id=10100000",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191210/14114491661d43.jpg?imageslim",
				      "sort_order": 9
				    },
				    {
				      "id": 3,
				      "name": "品牌馆",
				      "url": "/pages/order/order-list",
				      "icon_url": "http://pic.mercht.ficea.cn//upload/20191219/17512746672f98.jpg?imageslim",
				      "sort_order": 10
				    },
					{
					  "id": 1,
					  "name": "海淘购",
					  "url": "/pages/good/active-list?id=20",
					  "icon_url": "http://pic.mercht.ficea.cn//upload/20200215/152147205a18a6.png?imageslim",
					  "sort_order": 1
					}
				  ],
				  
				  "topicList": [
				  	{
				  		"title": "活动名称",
				  		"goodsList":[
				  			{
				  				"primaryPicUrl":"http://pic.mercht.ficea.cn//upload/20200221/092811843f5477.jpeg?imageslim",
				  				"productsIntroduction":"我说你必须买的商品啊hahah",
				  				"retailPrice":9.99
				  			},
							{
								"primaryPicUrl":"http://pic.mercht.ficea.cn//upload/20200221/092811843f5477.jpeg?imageslim",
								"productsIntroduction":"我说你必须买的商品啊",
								"retailPrice":9.99
							},
							{
								"primaryPicUrl":"http://pic.mercht.ficea.cn//upload/20200221/092811843f5477.jpeg?imageslim",
								"productsIntroduction":"我说你必须买的商品啊",
								"retailPrice":9.99
							},
							{
								"primaryPicUrl":"http://pic.mercht.ficea.cn//upload/20200221/092811843f5477.jpeg?imageslim",
								"productsIntroduction":"我说你必须买的商品啊",
								"retailPrice":9.99
							},
							{
								"primaryPicUrl":"http://pic.mercht.ficea.cn//upload/20200221/092811843f5477.jpeg?imageslim",
								"productsIntroduction":"我说你必须买的商品啊",
								"retailPrice":9.99
							},
							{
								"primaryPicUrl":"http://pic.mercht.ficea.cn//upload/20200221/092811843f5477.jpeg?imageslim",
								"productsIntroduction":"我说你必须买的商品啊",
								"retailPrice":9.99
							},
				  		]
				  	},
				  ],
			}
		      
		},
		onLoad() {

		},
		methods: {
       goodClassifyClick(index){
       	if(index==this.navIndex){
       		return
       	}
       	this.toTop()
       	this.navIndex=index
       	this.pageNo=1
       	this.isLastPage=false
       	if(index!=0){
       		this.queryTargetCategoryById(this.navList[index].id)
       		this.getCategoryGoodsList()
       	}
       },
		}
	}
</script>
<style>
	page{
		height: 100%;
	}
</style>
<style lang="scss" scoped>
	.content{
		min-height: 100%;
		background: white;
		box-sizing: border-box;
		padding-bottom: 100rpx;
		
	}
	.banner{
		width: 704rpx;
		height: 200rpx;
		display: block;
		margin: 20rpx auto;
		border-radius:15rpx ;
	}
	.good-header{
		//background-image: url(../../static/icon/v2_q0uiji.png);
		background-size:600rpx 100rpx;
		height: 100rpx;
		background-position: center;
		background-repeat:no-repeat ;
		line-height: 100rpx;
		text-align: center;
		color: rgba(229, 28, 35, 1);
		font-size: 40rpx;
		font-weight: bold;
	}
	.good-list{
		padding-top: 1rpx;
		.good-list-content{
			display: flex;
			flex-wrap: wrap;
			padding:0 20rpx 20rpx; 
		}
		.good-item{
			background: white;
			width: 338rpx;
			height: 440rpx;
			border-radius: 12rpx;
			overflow: hidden;
			margin-right: 25rpx;
			margin-bottom: 20rpx;
			&:nth-child(2n){
				margin-right: 0;
			}
		}
		.good-title{
			color: rgba(16, 16, 16, 1);
			font-size: 24rpx;
			display: -webkit-box;
			-webkit-box-orient: vertical;
			-webkit-line-clamp: 2;
			overflow: hidden;
		}
		.good-image{
			width: 338rpx;
			height: 314rpx;
			border-radius: 6rpx 6rpx 0px 0px;
		}
		.good-item-content{
			padding: 10rpx 20rpx;
		}
		.money{
			color: rgba(229, 28, 35, 1);
			font-size: 24rpx;
			font-weight: bold;
		}
	}
	
	.filtrate-box{
		height: 66rpx;
		
	}
	.filtrate-fixed{
		position: fixed;
		left: 0;
		top: 72rpx;
		background: white;
		z-index: 998;
	}
	
	.cart-box{
		width: 60rpx;
		border-radius:50rpx;
		background: white;
		box-shadow: 1rpx 2rpx 6rpx 0rpx rgba(0, 0, 0, 0.4);
		position: fixed;
		right: 50rpx;
		bottom: 150rpx;
		padding: 0 10rpx;
		box-sizing: border-box;
		.cart-item{
			height: 60rpx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			&:nth-child(2){
				border-top:1rpx solid rgba(0, 0, 0, 0.1);
			}
		}
		.cart-icon{
			height: 50rpx;
			width: 50rpx;
		}
	}
</style>


