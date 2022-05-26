<template>
	<view class="content">
		<!-- 登录页头部背景 -->
		<image class="index_bckground" :src="imgs.index_bckground" mode="widthFix"></image>
		<!-- 背景内容 -->
		<view class="bcgcontent">
			<image :src="imgs.logo" class="logo"></image>
			<text class="title">墨趣书法</text>
			<text class="detail">墨趣书法，用心教孩子书法</text>
			<view class="button" style="background:#C246BE;color:#FFFFFF; margin-top: 80rpx;">
				<text style="font-weight: 700;">学生进入</text>
			</view>
			<view class="button"style="background:#FFFFFF;color:#141F1F;">
				<text style="font-weight: 700;">教师进入</text>
			</view>
			<text class="detail" style="margin-top: 60rpx;">欢迎加入墨趣</text>
			<text class="detail">墨趣书法，让孩子爱上书法</text>
		</view>
		<view class="show_student_title">优秀学员展示</view>
		<scroll-view scroll-x="true" style="" >
			<view class="good_student">
				<!-- 从优秀学员数据表中获取数据 -->
				<view class="student" v-for="item in good_student">
					<image class="student_img" :src="server_img + item.student_img"></image>
					<view class="student_detail">{{item.student_level}}</view>
					<view class="student_detail">{{item.student_name}}</view>
				</view>
			</view>
		</scroll-view>
	
	</view>
</template>

<script>
	export default {
		data() {
			return {
				server_img: getApp().globalData.server_img,
				imgs:{
					'index_bckground': getApp().globalData.server_img + 'index_bckground.svg',
					'logo':  getApp().globalData.server_img + 'logo.svg'
				},
				good_student:[]
			}
		},
		onLoad() {
			var that = this
			uni.request({
				url: getApp().globalData.server + '/index.php/Home/Index/findgoodstudent',
				data: {
				
				},
				method: "POST",
				dataType: 'json',
				header: {
					'content-type': 'application/x-www-form-urlencoded' // 默认值
				},
				success(res) {
					console.log(res.data.data)
					that.good_student = res.data.data
				}
			})
		},
		methods: {

		}
	}
</script>

<style>
page{

}
.content{
	width: 100vw;
	height: 100vh;
}

.logo{
	width: 418rpx;
	height: 212rpx;
	margin-bottom: 30rpx;
}

.index_bckground{
	width: 100%;
	position: relative;
	z-index: 0;
}
.bcgcontent{
	width: 100%;
	position: absolute;
	top: 160rpx;
	z-index: 1;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
.title{
	font-style: normal;
	font-weight: 700;
	font-size: 48rpx;
	line-height: 135%;
	
	color: #FFFFFF;
}
.detail{
	font-style: normal;
	font-weight: 400;
	font-size: 28rpx;
	line-height: 150%;
	margin-top: 20rpx;
	color: #C9CECF;
}
.button{
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	margin-top: 30rpx;
	width: 450rpx;
	height: 100rpx;
	border-radius: 24rpx;
}
.show_student_title{
	margin-right: 20rpx;
	margin-top: 54rpx;
	font-style: normal;
	font-weight: 700;
	font-size: 32rpx;
	line-height: 150%;
	/* identical to box height, or 24px */
	
	text-align: right;
	
	color: #141F1F;

}
.student{
	width: 264rpx;
	height: 384rpx;
	margin: 24rpx 16rpx 24rpx 16rpx;
}
.student_img{
	width: 264rpx;
	height: 296rpx;
	border-radius: 10rpx;
}
.student_detail{
	font-style: normal;
	font-weight: 700;
	font-size: 24rpx;
	line-height: 32rpx;
	text-align: right;
	margin-right: 10rpx;

	color: #141F1F;
}
.good_student{
	display: flex;
	justify-content: space-around;
}
</style>
