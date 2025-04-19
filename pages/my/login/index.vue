<template>
	<form class='loginView' @submit="login">
		<view class="input-view">
			<view class="label-view">
				<text class="label">账号 </text>
			</view>
			<input class="input" type="text" placeholder="请输入用户名" name="nameValue" v-model="account"/>
		</view>
		<view class="input-view">
			<view class="label-view">
				<text class="label">密码</text>
			</view>
			<input class="input" type="password" placeholder="请输入密码" name="passwordValue" v-model="password"/>
		</view>
		<view class="button-view">
			<button type="default" class="login" hover-class="hover" formType="submit">登 录</button>
			<button type="default" class="register" hover-class="hover" @click="register">免费注册</button>
		</view>
	</form>
</template>

<script>
	import { showToast } from 'unit/index.js'
	export default {
		data () {
			return {
				account: '',
				password: '',
			}
		},
		methods:{
			login(e) {
				this.fromRul()
			},
			register() {
				uni.navigateTo({
					url: '/pages/my/register/index',
				});
			},
			fromRul() {
				if (!this.account) {
					showToast('用户名不能为空')
					return
				}
				if (!this.password) {
					showToast('密码不能为空')
					return
				}
			}
		}
	}
</script>

<style>
	.loginView {
		display: flex;
		flex: 1;
		flex-direction: column;
		padding-top: 30upx;
	}
	
	.input-view {
		border-bottom: 3upx solid #ddd;
		background-color: #fff;
		flex-direction: row;
		padding: 20upx;
		box-sizing: border-box;
	}
	
	.label-view {
		width: 100upx;
		height: 60upx;
		align-items: center;
		margin-right: 30upx;
	}
	
	.label {
		flex: 1;
		line-height: 60upx;
		font-size: 38upx;
		color: #555;
		text-align: left;
	}
	
	.input {
		flex: 1;
		height: 60upx;
		font-size: 38upx;
		align-items: center;
	}
	
	.button-view {
		margin-top: 50upx;
		padding: 0 20upx;
		box-sizing: border-box;
		flex-direction: column;
	}
	
	button {
		width: 100%;
		height: 80upx;
		line-height: 80upx;
		text-align: center;
		font-size: 38upx;
	}
	
	button.login {
		background-color: #1296db;
		color: #fff;
	}
	
	button.register {
		margin-top: 30upx;
		color: #1296db;
		background-color: #fff;
		border-color: #1296db;
		border-width: 2upx;
	}
	
	.register.hover,
	.login.hover {
		opacity: 0.6;
	}
</style>