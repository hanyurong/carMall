<template>
	<view class="service">
		<!-- tabBar -->
		<tab-bar :current="currentTabIndex" backgroundColor="#fbfbfb" color="#999" tintColor="#42b983" @click="tabClick"></tab-bar>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				currentTabIndex: 2
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.service {
	padding-bottom: 120rpx;
}
</style>
