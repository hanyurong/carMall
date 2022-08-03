<!-- 试货 -->
<template>
	<view class="tryGO">
		<view class="'topImg">
			<image v-if="sh" src="../../../static/image/home/shihuo.png"></image>
			<image v-else src="../../../static/image/home/qyImage.png"></image>
		</view>
		<view class="goodsList">
			<view class="uni-flex uni-column goodsItem"  v-for="(item,index) in goodsList" :key='index'>
				<view class="text">
					<image :src="item.imgSrc"></image>
				</view>
				<view class="text fontText" style="-webkit-flex: 1;flex: 1;">{{item.text}}</view>
				<view class="text money" style="-webkit-flex: 1;flex: 1;">￥{{item.money}}</view>
			</view>
		</view>
		<view class="tryGoods">
			<view class="shihuoLogo">
				<image v-if="sh" src="../../../static/image/home/sh.png" @click="toSH"></image>
				<image v-else src="../../../static/image/home/qyLogo.png" @click="toSH"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				sh: true,
				goodsList: [{
					imgSrc: '../../../static/image/home/banner1.png',
					text: '米家行车记录仪 GPS卫星全球定位 高清画面驱蚊器翁王企鹅驱蚊器王企鹅热污染',
					money: '2538.00'
				},{
					imgSrc: '../../../static/image/home/banner1.png',
					text: '米家行车记录仪 GPS卫星全球定位 高清画面',
					money: '2538.00'
				},{
					imgSrc: '../../../static/image/home/banner1.png',
					text: '米家行车记录仪 GPS卫星全球定位 高清画面地方',
					money: '111.00'
				},{
					imgSrc: '../../../static/image/home/banner1.png',
					text: '米家行车记录仪 GPS卫星全球定位 高清画面让人',
					money: '222.00'
				},{
					imgSrc: '../../../static/image/home/banner1.png',
					text: '米家行车记录仪 GPS卫星全球定位 高清画面驱蚊器',
					money: '33.00'
				}]
			}
		},
		onLoad(data) {
			if(data.shihuo === 'sh') {
				this.sh = true
			}else if(data.shihuo === 'qy'){
				this.sh = false
			}
		},
		methods: {
			toSH(e) {
				uni.switchTab({
					url: 'pages/tabBar/mall/mall'
				})
			},
		}
	}
</script>

<style lang="scss" scoped>
.tryGO {
	width: 750rpx;
	background: #FFFFFF;
	// height: 100%;
	margin-bottom: 300rpx;
	.topImg {
		image {
			width: 750rpx;
			height: 500rpx;
		}
	}
	.goodsList {
		border-radius: 16rpx;
		margin: -10rpx 30rpx 200rpx;
		height: 100%;
		.goodsItem {
			width: 47.2%;
			margin: 30rpx 20rpx 20rpx 0;
			float: left;
			image {
				width: 300rpx;
				height: 300rpx;
				margin: 20rpx 20rpx 30rpx;
			}
			.fontText {
				font-family: PingFangSC-Regular;
				font-weight: 400;
				font-size: 26rpx;
				color: #231F20;
				line-height: 36rpx;
				margin: 0 0 20rpx 20rpx;
				//文本超出部分以...形式展示
				text-overflow: -o-ellipsis-lastline;
				//整体超出部分隐藏
				overflow: hidden;
				//文本超出部分以...形式展示，同第一行样式代码
				text-overflow: ellipsis;
				//display 块级元素展示
				display: -webkit-box;
				//设置文本行数为2行
				-webkit-line-clamp: 2;
				//设置文本行数为2行
				line-clamp: 2;
				//从上到下垂直排列子元素（设置伸缩盒子的子元素排列方式）
				-webkit-box-orient: vertical;
			}
			.money {
				font-family: PingFangSC-Regular;
				font-weight: 400;
				font-size: 30rpx;
				color: #ED1C24;
				text-align: justify;
				margin-left: 20rpx;
			}
		}
	}
	.tryGoods {
		.shihuoLogo {
			position: fixed;
			right: 20rpx;
			bottom: 300rpx;
			image {
				width: 80px;
				height: 80px;
			}
		}
	}
}
</style>
