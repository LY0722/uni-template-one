<template>
	<form class='register-wrap' @submit="login">
		<view class="input-view">
			<view class="label-view">
				<text class="label">手机号 </text>
			</view>
			<input class="input" type="text" placeholder="请输入手机号" name="nameValue" v-model="account"/>
		</view>
		<view class="input-view">
			<view class="label-view">
				<text class="label">验证码 </text>
			</view>
			<input class="input code-input" placeholder="请输入验证码" name="passwordValue" v-model="vercode"/>
			<button class="getCode">获取验证码</button>
		</view>
		<view class="input-view">
			<view class="label-view">
				<text class="label">密码 </text>
			</view>
			<input class="input" type="password" placeholder="请输入密码" name="passwordValue" v-model="password"/>
		</view>
		<view class="button-view">
			<button type="default" class="login" hover-class="hover" formType="submit">注 册</button>
		</view>
	</form>
</template>

<script>
	import { showToast } from 'unit/index.js'
	export default {
		data () {
			return{
				account: '',
				vercode: '',
				password: '',
			}
		},
		methods:{
			login() {
				this.fromRul()
			},
			fromRul() {
				if (!this.account) {
					showToast('用户名不能为空')
					return
				}
				if (!this.vercode) {
					showToast('验证码不能为空')
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
	.register-wrap{
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
		width: 140upx;
		height: 60upx;
		align-items: center;
		margin-right: 30upx;
	}
	.code-input{
		width: 300upx;
	}
	.getCode{
		font-size: 35upx;
	}
	.button-view {
		margin-top: 50upx;
		padding: 0 20upx;
		box-sizing: border-box;
		flex-direction: column;
	}
	button.login {
		background-color: #1296db;
		width: 100%;
		color: #fff;
		line-height: 80upx;
		text-align: center;
		font-size: 38upx;
		border: none;
	}
	.login.hover {
		opacity: 0.6;
	}
</style>