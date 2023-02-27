<template>
	<view>
		<view>
			<image src="/static/crab.png" mode="aspectFill"></image>
		</view>
		<view class="contains">
			<uni-easyinput prefixIcon="person" v-model="username" placeholder="请输入用户名"></uni-easyinput>
		</view>
		<view class="contains">
			<uni-easyinput prefixIcon="locked" type="password" v-model="password" placeholder="请输入密码"></uni-easyinput>
		</view>
		<view>
			<u-row>
				<u-col :span="7">
					<view class="contains">
						<uni-easyinput v-model="yzm" placeholder="请输入验证码"></uni-easyinput>
					</view>
				</u-col>
				<u-col :span="5">
					<view class="contains">
						<image :src="codeUrl" @click="getCode" style="height: 40px; width: 100px;"/>
					</view>
				</u-col>
			</u-row>
		</view>
		<view class="contains">
			<u-button type="error" @click="doLogin">登录</u-button>
		</view>
	</view>
</template>

<script>
	
	import { getCodeImg,login } from "@/api/login.js";
	
	export default {
		data() {
			return {
				username:"",
				password:"",
				yzm:"",
				codeUrl:"",
				uuid:""
			}
		},
		onLoad() {
			this.getCode();
		},
		methods: {
			//登录
			doLogin(){
				//跳转到home
				uni.switchTab({
					url:'/pages/index/home'
				})
			},
			
			//获取验证码
			getCode(){
				getCodeImg().then(res => {
				  this.codeUrl = "data:image/gif;base64," + res.data.img;
				  this.uuid = res.data.uuid;
				});
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
