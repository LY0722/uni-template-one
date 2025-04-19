<template>
	<view class="shopp-car-wrap">
		<bclok class="shop-car-no-ord">暂无订单</bclok>
		<bclok class="shop-footer">
			<view class="shop-footer-row">
				<view class="shop-footer-item">
					<checkbox v-model="allSelect" class="checkbox-icon"></checkbox>
					全选
				</view>
				<view  class="shop-footer-item">
					<view class="total">合计: 
						<text class="money">￥27.00</text>
					</view>
					<view class="details">(共3件商品)</view>
				</view>
				<view  class="shop-footer-item">
					<button class="settlement-btn">结算</button>
				</view>
			</view>
		</bclok>
	</view>
</template>

<script>
	var self
	export default{
		data(){
			return{
				allSelect: false
			}
		}
	}
</script>

<style>
	.shopp-car-wrap{
		min-height: 100vh;
		background: #EFEFEF;
	}
	.shop-footer{
		height: 90upx;
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		display: block;
	}
	.shop-footer-row{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		background: #fff;
	}
	.shop-footer-item{
	}
	.settlement-btn{
		background: #1296db;
		color: #fff;
		border-radius: 0;
		height: 90upx;
		line-height: 90upx;
		font-size: 35upx;
		width: 140upx;
	}
	.total{
		position: absolute;
		top: 4upx;
		right: 150upx;
		font-size: 30upx;
		color: #6F6F6F;
	}
	.details{
		position: absolute;
		right: 150upx;
		font-size: 25upx;
		color: #888888;
	}
	.checkbox-icon{
		margin-left: 20upx;
	}
	checkbox .wx-checkbox-input{
		border-radius: 50%;
		height: 26rpx;
		width: 26rpx;
		margin-top: -4rpx;
		border: 1rpx solid #D1D1D1;
	}
	checkbox .wx-checkbox-input.wx-checkbox-input-checked::before {
		  width: 28rpx;
		  height: 28rpx;
		  line-height: 28rpx;
		  border-radius: 50%;
		  text-align: center;
		  font-size: 22rpx;
		  color: #C8C7CC;
		  background: #C8C7CC;
	}
	.money{
		color: #FF0000;
	}
	.shop-car-no-ord{
		width: 100%;
		text-align: center;
		padding: 10upx;
		color: #C8C7CC;
		font-size: 30upx;
	}
</style>