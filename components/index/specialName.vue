<template>
	<view class="spaecial-show">
		<view style="display: flex; align-items: center;">
			<view class="spaecial-show-title" style="margin-right: 20rpx;">专题名称</view>	
		</view>
		<view class="show-top">
			<view class="show-top-left">
				<image style="height: 300rpx; width: 300rpx;" mode="aspectFit" src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4047566459,3186528517&fm=26&gp=0.jpg"></image>
			</view>
			<view class="show-top-right">
				<image  src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4047566459,3186528517&fm=26&gp=0.jpg"></image>
				<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4047566459,3186528517&fm=26&gp=0.jpg"></image>
			</view>
		</view>
		<view class="show-bottpm">
			<image style="height: 320rpx; width: 100%;"  src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1585912817747&di=da2e40bd8253912d76b440048f889f7e&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01a5615545fc460000005b03c20789.jpg%401280w_1l_2o_100sh.jpg" mode=""></image>
		</view>
	</view>
</template>

<script>
</script>
<style lang="scss" scoped>
	.spaecial-show{
	padding: 0 25rpx;	
	.spaecial-show-title{
		color: rgba(16,16,16,1);
		font-weight: bold;
		font-size: 36rpx;
	}
	.show-top{
		padding-top: 20rpx;
		height: 320rpx;
		line-height: 320rpx;
		//text-align: center;
		width: 100%;
		display: flex; align-items: center;
		display: flex;
		justify-content: space-around;
		position: relative;
		.show-top-left{
			height: 308rpx;
			width: 300rpx;
			image{
				border-radius: 12rpx;
			}
		}
		.show-top-right{
			height: 308rpx;
			width: 380rpx;
			display: flex;
			flex-direction: column;
			image{
				margin-top: 8rpx;
				border-radius: 12rpx;
				height: 46%; 
				width: 100%;
				
			}
			
		}
		
	}
	.show-bottpm>image{
		border-radius: 12rpx;
	}	
	}
	
</style>

