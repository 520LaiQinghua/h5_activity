<template>
	<view class="bg">
		<swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="5000" :duration="500" :circular="true">
			<swiper-item v-for="(item,index) in list" :key="index" @click="toUrl(item.link)">
				<view class="swiper-item">
					<image class="swiper-image" :src="item.imageUrl"></image>
				</view>
			</swiper-item>
		</swiper>
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
			toUrl(url){
				if(url){
					uni.navigateTo({
						url:url
					})
				}
			},
		}
	}
</script>
<style lang="scss" scoped>
	.bg{
		background: white;
		//padding: 10rpx 0;
	}
	.swiper{
		width: 710rpx;
		height: 268rpx;
		border-radius:15rpx ;
		overflow: hidden;
		margin:  auto;
		.swiper-item{
			height: 100%;
			width: 100%;
			border-radius:15rpx ;
			overflow: hidden;
		}
		.swiper-image{
			height: 100%;
			width: 100%;
			border-radius:15rpx ;
		}
	}
</style>