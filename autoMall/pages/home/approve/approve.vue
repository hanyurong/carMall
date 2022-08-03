<!-- 认证 -->
<template>
	<view class="approve">
		<view class="content">
			<view class="msgList">
				<text>用户昵称</text>
				<input v-model="myName" type="text" />
			</view>
			<view class="msgList">
				<text>手机号码</text>
				<input @input="leaveInput" v-model="myPhone" type="text" />
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

<style lang="scss" scoped>
 .aprove{
	 .content {
		 margin: 20rpx 0 125rpx;
		 width: 750rpx;
		 height: 1135rpx;
		 background: #FFFFFF;
		 border-radius: 16rpx;
		 padding: 0 20rpx;
		 background: #FFFFFF;
		 box-shadow: 0px 4rpx 28rpx 0px rgba(0, 0, 0, 0.12);
		 border-radius: 24rpx;
		 margin-bottom: 24rpx;
		 font-size: 28rpx;
		 color: #999999;
		 input{
		 	display: block;
		 	width: 450rpx;
		 	height: 80rpx;
		 	line-height: 80rpx;
		 	float: right;
		 	margin-top: 20rpx;
		 	font-size: 28rpx;
		 	color: #333333;
		 	text-align: right;
		 	outline: none;
		 	border: 0;
		}
	 }
 }
</style>
