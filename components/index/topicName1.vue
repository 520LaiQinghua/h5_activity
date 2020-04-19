<template>
	<view class="topicName1">
		<view style="display: flex; align-items: center;">
			<view class="spaecial-show-title" style="margin-right: 20rpx;">主题名称1</view>	
		</view>
		<!-- 第一板块 -->
		<view class="topicname1-main">
			<view class="show-bottpm">
				<image style="height: 320rpx; width: 100%;"  src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1585912817747&di=da2e40bd8253912d76b440048f889f7e&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01a5615545fc460000005b03c20789.jpg%401280w_1l_2o_100sh.jpg" mode=""></image>
			</view>
				<scroll-view scroll-x class="good-list-content" >
					<view style="padding-top: 5rpx; white-space: nowrap;">
						<view class="good-item" v-for="(item,index) in list" :key="index" @click="toGoodDetail(item.id)">
							<image class="good-image" :src="item.primaryPicUrl"></image>
							<view class="productsIntroduction">{{item.productsIntroduction}}</view>
							<view class="money">{{item.retailPrice}}元</view>
				
						</view>
					</view>
				</scroll-view>
		</view>
		
		<!-- 第二板块 -->
		<view class="topicname1-main">
			<view class="show-bottpm">
				<image style="height: 320rpx; width: 100%;"  src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1585912817747&di=da2e40bd8253912d76b440048f889f7e&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01a5615545fc460000005b03c20789.jpg%401280w_1l_2o_100sh.jpg" mode=""></image>
			</view>
				<scroll-view scroll-x class="good-list-content" >
					<view style="padding-top: 5rpx; white-space: nowrap;">
						<view class="good-item" v-for="(item,index) in list" :key="index" @click="toGoodDetail(item.id)">
							<image class="good-image" :src="item.primaryPicUrl"></image>
							<view class="productsIntroduction">{{item.productsIntroduction}}</view>
							<view class="money">{{item.retailPrice}}元</view>
				
						</view>
					</view>
				</scroll-view>
		</view>
			<!-- 第三板块-->
			<view class="topicname1-main">
				<view class="show-bottpm">
					<image style="height: 320rpx; width: 100%;"  src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1585912817747&di=da2e40bd8253912d76b440048f889f7e&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01a5615545fc460000005b03c20789.jpg%401280w_1l_2o_100sh.jpg" mode=""></image>
				</view>
					<scroll-view scroll-x class="good-list-content" >
						<view style="padding-top: 5rpx; white-space: nowrap;">
							<view class="good-item" v-for="(item,index) in list" :key="index" @click="toGoodDetail(item.id)">
								<image class="good-image" :src="item.primaryPicUrl"></image>
								<view class="productsIntroduction">{{item.productsIntroduction}}</view>
								<view class="money">{{item.retailPrice}}元</view>
					
							</view>
						</view>
					</scroll-view>
			</view>
	</view>
</template>

<script>
	export default {
		props:{
			list:{
				type: Array,
				required: false,
				default:()=>[]
			},
			
		},
	}
</script>

<style lang="scss" scoped>
	.topicName1{
		padding: 0 25rpx;
		.spaecial-show-title{
			color: rgba(16,16,16,1);
			font-weight: bold;
			font-size: 36rpx;
		}
		.topicname1-main{
			padding: 20rpx 0;
		}
		.show-bottpm>image{
			border-radius: 12rpx;
		}	
		.good-list-content{
			flex-wrap: wrap;
			//padding:0rpx 20rpx 20rpx; 
			width: 750rpx;
			box-sizing: border-box;
		}
		.good-item{
			background: white;
			width: 190rpx;
			height: 250rpx;
			border-radius: 12rpx;
			overflow: hidden;
			margin-right: 20rpx;
			display: inline-block;
			text-align: center;
			box-sizing: border-box;
		}
		
		.good-image{
			width: 208rpx;
			height: 208rpx;
			border-radius: 6rpx 6rpx 0px 0px;
		}
		.money{
			color: rgba(229, 28, 35, 1);
			font-size: 26rpx;
			font-weight: bold;
		}
		.productsIntroduction{
			text-overflow:ellipsis;
			overflow:hidden;
			color: #101010;
			font-size: 22rpx;
		}
		
	}
</style>
