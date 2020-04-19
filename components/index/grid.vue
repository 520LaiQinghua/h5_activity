<template>
	<view class="grid">
		<!-- <view class="grid-header">
			<view>
				<text class="active">正</text>
				<text>品保障</text>
			</view>
			<view>
				<text class="active">官</text>
				<text>方直营</text>
			</view>
		</view> -->
		<view class="grid-flex">
			<view class="grid-item" v-for="(item,index) in list" :key="index" @click="gridItemClick(item.url)">
				<image class="gird-icon" :src="item.icon_url"></image>
				<!-- <view class="gird-icon" :style="'background:'+item.bgColor">{{item.title}}</view> -->
				<view class="gird-text">{{item.name}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			list:{
				type: Array,
				required: true,
				default:()=>[]
			},
		},
		methods:{
			gridItemClick(url){
				if(url=='/pages/tabbar/my'){
					uni.switchTab({
						url:url
					})
					return
				}
				if(url=='/pages/order/order-list'){
					if(!global.isLogin){
						uni.navigateTo({
							url:'/pages/user/login'
						})
						return
					}
					uni.navigateTo({
						url:url
					})
					return
				}
				
				uni.navigateTo({
					url:url
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.grid{
		padding: 0 25rpx ;
		background: white;
		.grid-flex{
			display: flex;
			flex-wrap: wrap;
		}
		.grid-item{
			width: 140rpx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			height: 160rpx;
		}
		.gird-icon{
			width: 80rpx;
			height: 80rpx;
			line-height: 80rpx;
			border-radius: 50%;
			// background-color: rgba(139, 195, 74, 1);
			text-align: center;
			color: white;
			font-size: 44rpx;
			font-weight: bold;
		}
		.gird-text{
			color: rgba(16, 16, 16, 1);
			font-size: 24rpx;
			text-align: center;
			margin-top: 10rpx;
			width: 100%;
			overflow: hidden;
			text-overflow:ellipsis;
			white-space: nowrap;
		}
		.grid-header{
			display: flex;
			justify-content: space-between;
			padding:0 175rpx;
			color: rgba(16, 16, 16, 1);
			font-size: 24rpx;
			.active{
				width: 36rpx;
				height: 36rpx;
				line-height: 36rpx;
				border-radius: 5rpx;
				background-color: rgba(229, 28, 35, 1);
				color: white;
				padding: 0 5rpx;
			}
		}
	}
</style>