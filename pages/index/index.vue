<template>
	<view class="content">
		<view class="top">
			<u-tabs  bg-color="#ffffff" :list="list" :is-scroll="false" :current="current" @change="change"></u-tabs>
		</view>
		
		<view class="below">
			<view class="contents" v-for="(itme,index) in 5" :key="index">
				<view class="contents_neo">
					<view class="shop">
						<image style="width: 40rpx; height: 40rpx;" src="../../static/shop.png"></image>
					</view>
					<view class="font">
						cdf会员购北京
					</view>
					<view class="more">
						<image style="width: 30rpx; height: 30rpx;" src="../../static/more.png"></image>
					</view>
					<view style="width: 20%;text-align: center;">
						<image style="width: 100rpx; height: 100rpx;" src="../../static/Settlement.png"></image>
					</view>
				</view>
				<view class="contents_two">
					<view class="commodity">
						<image style="width: 170rpx; height: 170rpx;" src="../../static/commodity.png"></image>
					</view>
					<view class="commodity_font">
						<view class=" text-black text-bold" style="font-size: 28rpx;">
							肌肤之映光凝前霜 37MLX2  ￥178.00
						</view>
						<view style="color: #A4A4A6; margin-top: 3%;">
							创建时间: 2020-09-01 17:22:03
						</view>
						<view style="color: #A4A4A6; margin-top: 1%;">
							锁单时间: 2020-09-01 17:22:03
						</view>
						<view style="color: #A4A4A6; margin-top: 1%; display: flex;">
							<view style="margin-top: 1%;">支付时间:</view>
							<view style="width: 50%; height: 50rpx; background-color: #FEEBE5; border-radius: 25rpx; display: flex;">
								<view style="width: 80%; margin-top: 2%; color: #E49389; text-align: center;"><text>去支付订单</text></view>
								<view style="width: 15%; margin-top: 4.2%; text-align: left;"><image style="width: 30rpx; height: 30rpx; " src="../../static/more.png"></image></view>
							</view>
						</view>
						
					</view>
				</view>
				<u-gap height="20" bg-color="#ffffff"></u-gap>
				<view style="width: 95%; display: flex; margin: auto;">
					<view style="width: 65%; text-align: right;">
						<u-button size="mini" shape="circle">再来一单</u-button>
					</view>
					<view style="width: 35%; text-align: right;">
						<u-button  type="warning" size="mini" shape="circle" :plain="true">分享得500积分</u-button>
					</view>
				</view>
				<view style="height: 10px;"></view>
			</view>
		</view>
		
		<view style="width: 100%; height: 20px;">
			<u-loadmore :status="status" />
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					name: '全部'
				}, {
					name: '待下单'
				}, {
					name: '待结算',
					count: 2
				}, {
					name: '已结算'
				}, {
					name: '已作废'
				}],
				current: 0,
				commoditylist:[
					{
						name:'',
					}
				],
				status: 'nomore',
			}
		},
		onLoad() {

		},
		methods: {
			change(index) {
				this.current = index;
			}
		}
	}
</script>

<style>
	page {
		width: 100%;
	}
	.content{
		width: 100%;
	}
	.top{
		width: 100%;
	}
	.below{
		width: 93%;
		margin: auto;
	}
	.contents{
		width: 100%;
		background-color: #ffffff;
		margin-top: 3%;
		border-radius: 10rpx;
		
	}
	.contents_neo{
		width: 100%;
		display: flex;
		border-bottom: 1rpx solid #FAF9FC;
	}
	.shop{
		margin-top: 5%;
		margin-left: 5%;
	}
	.more{
		width: 40%;
		margin-top: 5.5%;
	}
	.font{
		margin-left: 2%;
		line-height: 4;
	}
	.contents_two{
		width: 95%;
		margin: auto;
		display: flex;
	}
	.commodity{
		margin-top: 5%;
	}
	.commodity_font{
		margin-top: 2%;
		margin-left: 4%;
	}
</style>
