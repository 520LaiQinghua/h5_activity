<template>
	<view class="topicName2">
		<view style="display: flex; align-items: center;">
			<view class="spaecial-show-title" style="margin-right: 20rpx;">主题名称2</view>	
		</view>
		<view class="topicName2Main">
			<scroll-view scroll-x class="good-list-content" >
				<view style="padding-top: 5rpx; white-space: nowrap;">
					<view class="good-item" v-for="(item,index) in list" :key="index" @click="toGoodDetail(item.id)">
						<image class="good-image" :src="item.primaryPicUrl"></image>
						<view class="productsIntroduction">{{item.productsIntroduction}}</view>
						<view class="money">{{item.retailPrice}}元</view>
			
					</view>
				</view>
			</scroll-view>
			<scroll-view class="nav-left" scroll-x :scroll-left="viewScrollLeft" @scroll="viewScroll" @scrolltolower="scrolltolower">
				<view class="nav-left-item" v-for="(item,index) in list2" :key="index" :class="{active:index==navIndex}"  @click="goodClassifyClick(index)">{{item.name}}</view>
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
			list2:{
				type: Array,
				required: true,
				default:()=>[]
			},
			navIndex:{
				type: Number,
				required: true,
				default:0
			}
			
		},
		data(){
			return{
				viewScrollLeft:0
			}
		},
		methods:{
			toSearch(){
				uni.navigateTo({
					url:'/pages/search/search'
				})
			},
			scrolltolower(e){
				console.log(e)
			},
			viewScroll(e){
				this.viewScrollLeft = e.detail.scrollLeft
			},
			viewScrollToLeft(e){
				this.viewScrollLeft = 0
			},
			goodClassifyClick(index){
				this.$emit('goodClassifyClick',index)
			},
			toGoodClassify(){
				uni.navigateTo({
					//url:'/pages/good/classify'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.topicName2{
		padding: 0 25rpx;
		.spaecial-show-title{
			color: rgba(16,16,16,1);
			font-weight: bold;
			font-size: 36rpx;
		}
		.topicName2Main{
			
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
			.nav-left{
				width: 750rpx;
				height: 72rpx;
				padding-left: 20rpx;
				box-sizing: border-box;
				// display: flex;
				zoom: 1;
				overflow: hidden;
				white-space: nowrap;
				.nav-left-item{
					// float: left;
					display: inline-block;
					padding: 0 5rpx;
					margin-right: 20rpx;
					// flex: 1;
					line-height: 66rpx;
					color: rgba(130, 130, 130, 242);
					font-size: 28rpx;
					text-align: center;
					box-sizing: border-box;
					border-bottom: 6rpx solid transparent;
					&.active{
						font-size: 32rpx;
						// border-bottom: 6rpx solid rgba(255, 255, 255, 1);
						color: rgba(255, 255, 255, 1);
						font-weight:bold ;
						position: relative;
						&::after{
							content: '';
							width: 34rpx;
							height: 0;
							border-top: 4rpx solid rgba(255, 255, 255, 1);
							position: absolute;
							bottom: 5rpx;
							left: 50%;
							transform: translateX(-50%);
						}
					}
				}
			}
		}
	}
	
</style>
