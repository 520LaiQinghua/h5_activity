<template>
	<view class="good-list" v-if="list.length>0">
		<view class="good-list-header">
			<view style="display: flex; align-items: center;">
				<view class="good-list-title" style="margin-right: 20rpx;"> {{title}}</view>	
			</view>
			<view style="display: flex; align-items: center;">
				<view class="desc">距离活动结束还有</view>
				<uni-countdown @timeup="timeup" color="#FFFFFF" :show-day="false" background-color="#DBD8D8" splitor-color="#DBD8D8" border-color="#FC4444" :hour="hours" :minute="minutes" :second="seconds"></uni-countdown>
			</view>
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
</template>

<script>
	import uniCountdown from '@/components/uni-ui/uni-countdown.vue'
	export default {
		components:{uniCountdown},
		props:{
			list:{
				type: Array,
				required: false,
				default:()=>[]
			},
			title:{
				type: String,
				default:'',
				
			},
		},
		data(){
			return{
				hours: 0,
				minutes: 0,
				seconds: 0
			}
		},
		mounted() {
			this.timeup();
		},
		methods:{
			timeup(){
				var nowDate = new Date()
				var tomorrow = new Date(new Date(new Date().toLocaleDateString()).getTime() +24 * 60 * 60 * 1000)
				var timestamp = tomorrow.getTime() - nowDate.getTime();   //时间差的毫秒数    
				//计算出相差天数  
				var days = Math.floor(timestamp / (24 * 3600 * 1000))
				//计算出小时数  
				var leave1 = timestamp % (24 * 3600 * 1000)    //计算天数后剩余的毫秒数  
				var hours = Math.floor(leave1 / (3600 * 1000))
				//计算相差分钟数  
				var leave2 = leave1 % (3600 * 1000)        //计算小时数后剩余的毫秒数  
				var minutes = Math.floor(leave2 / (60 * 1000))
				//计算相差秒数  
				var leave3 = leave2 % (60 * 1000)      //计算分钟数后剩余的毫秒数  
				var seconds = Math.round(leave3 / 1000)
				this.hours = hours
				this.minutes = minutes
				this.seconds = seconds
				console.log(hours, minutes, seconds)
			},
			// toGoodDetail(id){
			// 	uni.navigateTo({
			// 		url:'/pages/good/detail?id='+id
			// 	})
			// }
		}
	}
</script>
<style lang="scss" scoped>
	.good-list-header{
		padding: 15rpx 20rpx;
		display: flex;
		align-items: center;
		position: relative;
		background: white;
		 justify-content: space-between;
		.good-list-title{
			color: rgba(16,16,16,1);
			font-weight: bold;
			font-size: 36rpx;
		}
	}
	.good-list{
		padding-top: 1rpx;
		background: white;
		.good-list-content{
			flex-wrap: wrap;
			padding:0rpx 20rpx 20rpx; 
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
		.good-title{
			height: 64rpx;
			color: rgba(16, 16, 16, 1);
			font-size: 24rpx;
			display: -webkit-box;
			-webkit-box-orient: vertical;
			-webkit-line-clamp: 2;
			overflow: hidden;
		}
		.good-image{
			width: 208rpx;
			height: 208rpx;
			border-radius: 6rpx 6rpx 0px 0px;
		}
		.good-item-content{
			padding: 10rpx 20rpx;
		}
		.money-box{
			display: flex;
			justify-content: space-between;
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
		// .productsIntroduction:hover{
		// 	overflow:visible;
		// }
	}
	.good-list-header {
		/deep/ .uni-countdown__number{
			border-radius:10rpx ;
			line-height: 40rpx;
			height: 40rpx;
			width: 45rpx;
		}
		/deep/ .uni-countdown__splitor{
			line-height: 40rpx;
			height: 40rpx;
		}
	}
	.desc{
		color: #AFAEAE ;
		font-size: 24rpx;
		line-height: 60rpx;
		font-weight: bold;
		padding-right: 10rpx;
	}
</style>

