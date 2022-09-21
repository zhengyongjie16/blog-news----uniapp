<template>
	<view class="content">
	  <view class="jiangqie-scroll-nav">
		<scroll-view
		  scroll-x
		  scroll-with-animation
		  scroll-left="scrollLeft"
		  show-scrollbar="false"
		  class="jiangqie-tab-nav"
		>
		  <view
			@click="change(1)"
			:class="{ 'jiangqie-tab-on': changelist == 1 }"
		  >
			<view>全部动态</view>
		  </view>
		  <view
			@click="change(2)"
			:class="{ 'jiangqie-tab-on': changelist == 2 }"
		  >
			<view>项目案例</view>
		  </view>
		</scroll-view>
	  </view>
  
	  <!-- 全部动态 -->
	  <scroll-view class="main_box" scroll-y="true" @scrolltolower="lower" v-if="changelist==1">
		<template>
		  <view
			class="jiangqie-block"
			@click="clickLink('https://liubing.me/google-mirror.html')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">分享几个可用的谷歌镜像</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2015/02/02/15/28/bar-621033_960_720.jpg'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 329</text>
				<text>2022-4-22</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <view
			class="jiangqie-block"
			@click="clickLink('https://liubing.me/google-mirror.html')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">uniapp lb-picker选择器</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2016/04/14/07/56/icon-1328421_960_720.jpg'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 62</text>
				<text>2022-1-04</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <view
			class="jiangqie-block"
			@click="clickLink('https://liubing.me/google-mirror.html')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">wordpress优化，整站资源CDN处理</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://img0.baidu.com/it/u=1358779379,2958771478&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=312'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 198</text>
				<text>2021-9-12</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <view
			class="jiangqie-block"
			@click="clickLink('https://liubing.me/recommend-several-free-unlimited-cdns.html')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">推荐几款免费且不限流量的全球CDN</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://img1.baidu.com/it/u=1648885844,2590868475&fm=253&fmt=auto&app=138&f=JPG?w=500&h=333'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 77</text>
				<text>2021-8-22</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <view
			class="jiangqie-block"
			@click="clickLink('https://hengxingstu.github.io/2022/05/02/forwardAndBackwordSlash/')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">正斜杠(" / ")和反斜杠(" \ ")的区别</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://w.wallhaven.cc/full/6o/wallhaven-6o6orw.png'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 24</text>
				<text>2022-5-02</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <view
			class="jiangqie-block"
			@click="clickLink('https://hengxingstu.github.io/2022/04/26/%5BYoutube%5DSpringBoot+Angular%E5%AE%9E%E6%88%98/')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">Youtube_SpringBoot+Angular实战</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://wallpapercave.com/uwp/uwp2365506.jpeg'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 33</text>
				<text>2022-4-26</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <view
			class="jiangqie-block"
			@click="clickLink('https://baike.baidu.com/item/%E7%94%B3%E6%A0%B9%E7%AD%BE%E8%AF%81/6655513')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">申根签证 - 百度百科</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://w.wallhaven.cc/full/x8/wallhaven-x8rj8v.jpg'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 12</text>
				<text>2018-4-29</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <uni-load-more :status="loadMore"></uni-load-more>
		</template>
	  </scroll-view>
  
	  <!-- 项目案例 -->
	  <scroll-view class="main_box" scroll-y="true" @scrolltolower="lower" v-if="changelist==2">
		<template>
		  <view
			class="jiangqie-block"
			@click="clickLink('https://github.com/zhengyongjie16')"
		  >
			<view class="jiangqie-list">
			  <view class="jiangqie-list-title">这只是个人的资源，无法展示企业内容</view>
			  <view class="jiangqie-list-img">
				<image mode="aspectFill" :src="'https://w.wallhaven.cc/full/6o/wallhaven-6o6orw.png'"></image>
			  </view>
			  <view class="jiangqie-list-text">
				<view class="jiangqie-list-data">
				  <text>浏览 23</text>
				<text>2021-12-12</text>
				</view>
			  </view>
			</view>
		  </view>
  
		  <uni-load-more :status="loadMore"></uni-load-more>
		</template>
	  </scroll-view>
  
	</view>
  </template>

<script>

	import Util from '@/utils/util';
	import Api from '@/utils/api';
	import Rest from '@/utils/rest';

	export default {
		data() {
			return {
				top_navs: [],
				curCat: 0,
				
				posts: [],
				loadMore: 'more',
				changelist:1
			}
		},

		onLoad(options) {
			if (options.cat_id) {
				this.curCat = options.cat_id;
			}
			
			this.loadSetting();
			this.loadPost();
		},

		onShow() {
			// #ifdef MP-BAIDU
			swan.setPageInfo({
				title: '最新资讯_' + getApp().globalData.appName,
				description: getApp().globalData.appDesc,
				keywords: getApp().globalData.appKeyword,
			});
			// #endif
		},

		onShareAppMessage() {
			let params = {
				title: getApp().globalData.appName + ' 最新资讯'
			};

			// #ifdef MP-WEIXIN || MP-BAIDU
			params.path = 'pages/list/list';
			// #endif

			return params;
		},

		// #ifdef MP-WEIXIN
		onShareTimeline() {
			return {
				title: etApp().appName + ' 最新资讯'
			};
		},
		onAddToFavorites(res) {
			return {
				title: etApp().appName + ' 最新资讯'
			};
		},
		// #endif

		onReachBottom() {
			if (this.loadMore == 'more') {
				this.loadPost();
			}
		},

		methods: {
			change(id){
				this.changelist = id
			},
			/**
			 * 点击文章
			 */
			clickPost(post_id) {
				Util.openLink('/pages/detail/detail?post_id=' + post_id);
			},

			/**
			 * 点击分类
			 */
			clickNavCat(cat_id) {
				this.curCat = cat_id;
			
				this.loadMore = 'more';
				this.loaded = false;
				this.posts = [];
			
				this.loadPost();
			},
			
			/**
			 * 加载配置
			 */
			loadSetting() {
				Rest.post(Api.JQ_OW_FREE_SETTING_NEWS, {}).then(res => {
					this.top_navs = [{
						id: 0,
						name: '全部'
					}];
					this.top_navs = this.top_navs.concat(res.data.top_nav);
				}, err => {
					console.log(err)
				});
			},
			
			/**
			 * 加载文章
			 */
			loadPost() {
				if (this.loadMore == 'loading') {
					return;
				}
				this.loadMore = 'loading';

				Rest.post(Api.JQ_OW_FREE_POSTS_LAST, {
					offset: this.posts.length,
					cat_id: this.curCat,
				}).then(res => {
					this.posts = this.posts.concat(res.data.posts);
					this.loadMore = res.data.more;
				});
			}
		}
	}
</script>

<style lang="scss" scoped>
	.jiangqie-block-margin {
		margin-top: 100rpx;
	}

	.jiangqie-block:first-of-type {
		border: none;
		border-top: 16rpx solid #F3F3F3;
	}
</style>
