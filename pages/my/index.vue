<template>
	<view class="my_wrap">
		<view class="logo" @click="goLogin" :hover-class="!login ? 'logo-hover' : ''">
			<image class="logo-img" :src="login ? uerInfo.avatarUrl :avatarUrl"></image>
			<view class="logo-title">
				<text class="uer-name">Hi，{{login ? uerInfo.name : '木木'}}</text>
				<text class="iconfont login-icon-color" v-if="!login">&#xe604;</text>
			</view>
		</view>
		
		<view class="my-order">
			<view class="my-order-title">
				<text>我的订单</text>
			</view>
			
			<view class="my-order-list">
				<view class="my-order-item ">
					<text class="iconfont my-order-icon">&#xe607;</text>
					<text class="my-order-title">待付款</text>
				</view>
				<view class="my-order-item ">
					<text class="iconfont my-order-icon">&#xe66c;</text>
					<text class="my-order-title">待发货</text>
				</view>
				<view class="my-order-item">
					<text class="iconfont my-order-icon">&#xe60c;</text>
					<text class="my-order-title">待收货</text>
				</view>
				<view class="my-order-item ">
					<text class="iconfont my-order-icon">&#xe684;</text>
					<text class="my-order-title">已收货</text>
				</view>
			</view>
		</view>
		
		<view class="center-list">
			<view class="center-list-item border-bottom">
				<text class="iconfont">&#xe618;</text>
				<text class="list-text">我的收藏</text>
				<text class="iconfont">&#xe604;</text>
			</view>
			<view class="center-list-item border-bottom">
				<text class="iconfont">&#xe61d;</text>
				<text class="list-text">收货地址</text>
				<text class="iconfont">&#xe604;</text>
			</view>
			<view class="center-list-item">
				<text class="iconfont">&#xe608;</text>
				<text class="list-text">关于我们</text>
				<text class="iconfont">&#xe604;</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				login:false,
				avatarUrl:"../../static/logo.png",
				uerInfo:{},
			}
		},
		methods:{
			goLogin() {
				if(!this.login){
					uni.navigateTo({
						url:"/pages/my/login/index"
					})
				}
			}
		}
	}
</script>

<style>
	
	.my_wrap {
		background: #EFEFEF;
		min-height: 100vh;
		display: flex;
		flex-direction: column;
	}
	.logo {
		height: 240upx;
		padding: 20upx;
		box-sizing: border-box;
		background-color: #FF80AB;
		flex-direction: row;
		align-items: center;
	}
	.logo-hover {
		opacity: 0.8;
	}
	.logo-img {
		width: 150upx;
		height: 150upx;
		border-radius: 150px;
	}
	.logo-title {
		height: 150upx;
		flex: 1;
		align-items: center;
		justify-content: space-between;
		flex-direction: row;
		margin-left: 20upx;
	}
	.uer-name {
		overflow: hidden;
		text-overflow:ellipsis;
		white-space: nowrap;
		width: 300upx;
		height: 60upx;
		line-height: 60upx;
		font-size: 38upx;
		color: #FFFFFF;
	}
	.login-title {
		height: 150upx;
		align-items: self-start;
		justify-content: center;
		flex-direction: column;
		margin-left: 20upx;
	}
	.login-icon-color{
		color: #fff;
	}
	/* 收藏列表 */
	.center-list {
		flex: 1;
		margin-top: 20upx;
		flex-direction: column;
	}
	.center-list-item {
		height: 90upx;
		box-sizing: border-box;
		flex-direction: row;
		padding: 0upx 20upx;
		background-color: #FFFFFF;
		align-items: center;
	}
	.border-bottom {
		border-bottom-width: 1upx;
		border-color: #c8c7cc;
		border-bottom-style: solid;
	}
	.list-icon {
		width: 40upx;
		height: 90upx;
		line-height: 90upx;
		font-size: 34upx;
		color: #FF80AB;
		text-align: center;
		font-family: texticons;
		margin-right: 20upx;
	}
	.list-text {
		padding-left: 15upx;
		height: 90upx;
		line-height: 90upx;
		font-size: 34upx;
		color: #555;
		flex: 1;
		text-align: left;
	}
	/*  我的订单 */
	.my-order{
		background: #fff;
		padding: 0 20upx;
		display: block;
	}
	.my-order-title{
		font-size: 34upx;
		color: #555;
		height: 90upx;
		line-height: 90upx;
	}
	.my-order-list{
		display: flex;
		justify-content: space-between;
	}
	.my-order-item{
		flex: 1;
		display: block;
		align-items: center;
		text-align: center;
	}
	.my-order-icon{
		display: block;
		text-align: center;
		font-size: 55upx;
	}
	.my-order-title{
		display: block;
	}
</style>