<!-- 购物车 -->
<template>
	<view class="shoppingCart">
		<view class="shopDelete" @click="deleteShop">
			<text>删除</text>
		</view>
		<view class="shopList">
			<!-- 空购物车 -->
			<view v-if="isEmptyCart" class="bg-color-white border-bottom-left-radius-xl border-bottom-right-radius-xl padding-lg">
				<view class="row-center-center">
					<image class="img-size-xl" src="/static/cart/empty-cart.png" mode="aspectFit"></image>
					<text class="font-size-lg text-color-greyblack">购物车是空的</text>
				</view>
			</view>
			<!-- 非空购物车 -->
			<view v-if="!isEmptyCart" class="shopItem" v-for="(item, index) in goodsList" :key="index">
				<view class="shopcheckbox" @click="chooseShop(item)">
					<checkbox :checked="item.checked" />
				</view>
				<image class="shopImage" :src="item.imgSrc" mode=""></image>
				<view class="flex-1 column-center-stretch padding-left-lg">
					<text class="lines-2 font-size-base">{{item.title}}</text>
					<!-- <view class="row-start-center margin-v-side-base">
						<view class="row-center-center bg-color-grey border-radius-rect-circle padding-side-base padding-v-side-xs">
							<text v-for="(property, propertyIndex) of product.sku" :key="propertyIndex" class="font-size-sm">{{property}},</text>
						</view>
					</view> -->
					
					<view class="row-between-center">
						<!-- <xg-money camel :size="UNI_FONT_SIZE_XL" :money="product.price"></xg-money> -->
						<view class="number-box">
							<uni-number-box :min="1" :value="item.count"  @change="onNumberBoxChange(product, $event)"></uni-number-box>
						</view>
					</view>
				</view>
			</view>
				
		</view>
	</view>
</template>

<script>
	import{uniNumberBox} from '@dcloudio/uni-ui'
	export default {
		components: {
			uniNumberBox,
		},
		data() {
			return {
				isEmptyCart: false,
				goodsList: [{
					imgSrc: require('../../../static/image/home/banner1.png'),
					title: '冲锋GP7617.3英寸11代i7游戏笔记本电脑256GB',
					type: '太空灰;256GB',
					money: '￥368.00',
					originMoney: '¥1642',
					count: '1',
					checked: true,
				},{
					imgSrc: require('../../../static/image/home/banner1.png'),
					title: '冲锋GP7617.3英寸11代i7游戏笔记本电脑256GB',
					type: '太空灰;256GB',
					money: '￥368.00',
					originMoney: '¥1642',
					count: '1',
					checked: true,
				},{
					imgSrc: require('../../../static/image/home/banner1.png'),
					title: '冲锋GP7617.3英寸11代i7游戏笔记本电脑256GB',
					type: '太空灰;256GB',
					money: '￥368.00',
					originMoney: '¥1642',
					count: '1',
					checked: true,
				}]
			}
		},
		methods: {
			//删除商品
			deleteShop() {
				
			}
		}
	}
</script>

<style lang="scss" scoped>
.shoppingCart {
	width: 750rpx;
	// padding: 0 30rpx;
	.shopDelete {
		height: 90rpx;
		line-height: 90rpx;
		padding: 0 30rpx;
		text-align: right;
		text {
			font-family: PingFangSC-Regular;
			font-weight: 400;
			font-size: 30rpx;
			color: #7D0016;
		}
	}
	.shopList {
		width: 750rpx;
		background: #FFFFFF;
		.shopItem {
			width: 750rpx;
			height: 230rpx;
			padding: 30rpx 30rpx 15rpx;
			display: flex;
			align-items: center;
			// flex-direction: column;
			// justify-content: center;
			.shopcheckbox {
				width: 32rpx;
				height: 32rpx;
				border: 1rpx solid #A9A9A9;
				border-radius: 16rpx;
			}
			.shopImage {
				width: 139rpx;
				height: 139rpx;
			}
		}
	}
}
</style>
