<template>
	<view>
		<!-- tabBar -->
		<tab-bar :current="currentTabIndex" backgroundColor="#fbfbfb" color="#999" tintColor="#42b983" @click="tabClick"></tab-bar>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				currentTabIndex: 3
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
