<template>
	<view class="content">
		<view class="index_title">
		<view class="titleone">
				<text>购物</text>
		</view>
			<view class="titletwo">
				<text class="titletwo1">沃银商城</text>
				<text class="titletwo2">全场支持万事通积分支付</text>
			</view>
		</view>
		<view class="search-box">
			<view class="search-input-box" @click="toSearch">
				<icon type="search" class="iconfont" size="18px"/>
				<input disabled class="search-input" placeholder="搜索商品名称或粘贴商品标题" />
				<!-- <view style="height: 100%;width: 100%;position: absolute;left:0;top: 0;"></view> -->
			</view>
			<view class="search-right">
				<view class="right-classify">
					<uni-icons type="list" size="22px"></uni-icons>
					<text style=" margin-top: -26rpx; font-size: 24rpx;">分类</text>
				</view>
				<view class="right-shoppingcart">
					<uni-icons type="cart" size="22px"></uni-icons>
					<text style=" margin-top: -26rpx; font-size: 24rpx;">购物车</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniIcons from "@/components/uni-icons/uni-icons.vue"
	export default {
		 components: {uniIcons},
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
        toSearch(){
        	uni.navigateTo({
        		url:'/pages/search/search'
        	})
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
		height: 100%;
		box-sizing: border-box;
	}
	.index_title{
		width: 580rpx;
		height: 60rpx;
		box-sizing: border-box;
		padding: 0 20rpx;
		font-weight: bold;
		
		.titleone{
			font-size: 32rpx;
			text-align: center;
			height: 60rpx;
			width: 64rpx;
			line-height: 60rpx;
			float: left;
		}
		.titletwo{
			height: 60rpx;
			font-size: 24rpx;
			display: flex;
			flex-direction:column;
			align-content: space-around;
			padding-left: 20rpx;
			.titletwo1{
				height: 50%;
				
			}
			.titletwo2{
				height: 50%;
			}
		}
		
	}
	
	.search-box{
		padding: 0 20rpx;
		margin-bottom: 40rpx;
		.search-input-box{
			margin-top: 15rpx;
			width: 514rpx;
			height: 64rpx;
			box-sizing: border-box;
			line-height: 62rpx;
			border-radius: 32rpx;
			background-color: rgba(251, 250, 250, 1);
			color: rgba(16, 16, 16, 1);
			font-size: 24rpx;
			border: 1rpx solid rgba(179, 178, 178, 1);
			//margin: auto;
			display: flex;
			align-items: center;
			position: relative;
			float: left;
			.iconfont{
				color: rgba(142, 142, 147, 1);
				font-size: 28rpx;
				padding: 0 14rpx;
			}
			.search-input{
				width: 514rpx;
				height: 48rpx;
				background-color: rgba(255, 255, 255, 0);
				color: rgba(136, 136, 136, 1);
				font-size: 28rpx;
			}
		}
		.search-right{
			height: 64rpx;
			box-sizing: border-box;
			line-height: 62rpx;
			display:flex;
			flex-wrap: nowrap;
			//float: right;
			//width: 128rpx;
			justify-content: space-around;
			.right-classify,.right-shoppingcart{
				display:flex;
				flex-direction:column;
				
				//flex-wrap: wrap;
				// width: 50%;
			}
		}
	}
	
</style>
