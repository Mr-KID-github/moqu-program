<template>
	<view>
		<view class="title">创建你的
		墨趣账号吧</view>
		<view class="content">
			<view class="input_something">
				<image class="input_logo" src="/static/icon/icon_phone.svg"></image>
				<input placeholder="电话" placeholder-class="placeholder_input"/>
			</view>
			<view class="input_something">
				<image class="input_logo" src="/static/icon/icon_password.svg"></image>
				<input password="true" placeholder="密码" placeholder-class="placeholder_input"/>
			</view>
			<view class="input_something">
				<image class="input_logo" src="/static/icon/icon_password_again.svg"></image>
				<input password="true" placeholder="确认密码" placeholder-class="placeholder_input"/>
			</view>
			<view class="sing_up_button" style="background: #4360C9;">
				<image src="/static/icon/icon_join.svg"></image>
				<text>加入墨趣</text>
			</view>
			<view class="or">
				<view class="line"></view>
				<text>或者微信授权登录</text>
				<view class="line"></view>
			</view>
			
			<view class="sing_up_button" style="background: #4ECB71;;">
				<image src="/static/icon/icon_wechat.svg"></image>
				<text>微信授权登录</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.or{
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 50rpx;
	}
	.or text{
		font-style: normal;
		font-weight: 800;
		font-size: 20rpx;
		line-height: 30rpx;
		/* identical to box height */
		
		text-align: center;
		
		color: #000000;
	}
	.line{
		width: 100rpx;
		height: 0rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		border: 1rpx solid #D6DAE8;
	}
	.placeholder_input{

		font-style: normal;
		font-weight: 700;
		font-size: 28rpx;
		line-height: 36rpx;
		
		color: #979797;
	}
	.input_something{
		width: 568rpx;
		height: 96rpx;
		display: flex;
		align-items: center;
		background: #EEEEEE;
		border-radius: 20rpx;
		margin-top: 50rpx;
	}
	.content{
		width: 100vw;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.sing_up_button{
		margin-top: 50rpx;
		width: 560rpx;
		height: 108rpx;
		

		border-radius: 40rpx;
		font-style: normal;
		font-weight: 700;
		font-size: 32rpx;
		line-height: 42rpx;
		/* identical to box height */
		
		display: flex;
		justify-content: center;
		align-items: center;
		
		color: #FFFFFF;
	}
	.sing_up_button image{
		position: fixed;
		left: 160rpx;
		width: 72rpx;
		height: 72rpx;
	}
	.input_logo{
		width: 48rpx;
		height: 48rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
	}

.title{
	width: 480rpx;
	height: 248rpx;
	margin-left: 32rpx;
	margin-top: 32rpx;

	font-style: normal;
	font-weight: 700;
	font-size: 96rpx;
	line-height: 124rpx;

	color: #000000;
}
</style>
