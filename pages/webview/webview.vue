<template>
	<view>
		<web-view :src="src"></web-view>
	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				src: 'http://zhengbbs.cn'
			};
		},

		onLoad(options) {
			if (options.src) {
				this.src = decodeURIComponent(options.src);
			}
			uni.setNavigationBarTitle({
				title: '南圣安地列斯'
			})
		},

		onShareAppMessage() {
			return {
				title: getApp().globalData.appName,
				path: 'pages/mix/webview/webview?src=' + encodeURIComponent(this.src)
			};
		},

		onShareTimeline() {
			return {
				title: getApp().globalData.appName
			};
		},
	}
</script>

<style lang="scss" scoped>

</style>
