<template>
	<view class="content">
		<scroll-view class="main_box" scroll-y="true">
			<!-- 留言表单 -->
			<view class="jiangqie-gust-img">
				<image class="image" mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2019/10/27/18/48/bridge-4582501_960_720.jpg'"></image>
			</view>
			<view class="jiangqie-block">
				<view v-if="title" class="jiangqie-head">{{title}}</view>
				<view class="jiangqie-form">
					<view class="jiangqie-form-line">
						<view>
							<text>姓名:</text>
						</view>
						<view>
							<input type="text" v-model="username" />
						</view>
					</view>
					<view class="jiangqie-form-line">
						<view>
							<text>电话:</text>
						</view>
						<view>
							<input type="text" v-model="phone" />
						</view>
					</view>
					<view class="jiangqie-form-line">
						<view>
							<text>E-mail:</text>
						</view>
						<view>
							<input type="text" v-model="email" />
						</view>
					</view>
					<view class="jiangqie-form-hightline">
						<view>
							<text>请输入留言内容:</text>
						</view>
						<view>
							<textarea auto-height="" v-model="content"></textarea>
						</view>
					</view>
					<!-- 认证button -->
					<view class="jiangqie-base-block jiangqie-form-btn">
						<view class="jiangqie-button" @click="clickSubmit()">提交</view>
					</view>
				</view>
			</view>
			<view @click="clickJiangQie" class="jiangqie-block jiangqie-brand">由 zhengbbs.cn 提供技术支持 备案编号：</view>
		</scroll-view>
	</view>
</template>

<script>

	import Util from '@/utils/util';
	import Alert from '@/utils/alert';
	import Api from '@/utils/api';
	import Rest from '@/utils/rest';

	export default {
		data() {
			this.load = false;
			
			return {
				background: undefined,
				title: '',

				username: '',
				phone: '',
				email: '',
				content: '',
			}
		},
		methods: {
			jqOnLoad() {
				Rest.post(Api.JQ_OW_FREE_SETTING_FEEDBACK, {}).then(res => {
					this.background = res.data.background;
					this.title = res.data.title;
				});
			},

			jqOnShow() {
				if (!this.load) {
					this.load = true;
					this.jqOnLoad();
				}
			},

			clickSubmit() {
				Rest.post(Api.JQ_OW_FREE_USER_FEEDBACK, {
					username: this.username,
					phone: this.phone,
					email: this.email,
					content: this.content
				}).then(res => {
					if (res.code == 0) {
						Alert.success('留言成功');
						this.username = '';
						this.phone = '';
						this.email = '';
						this.content = '';
					} else {
						Alert.error(res.msg);
					}
				});
			},
			
			clickJiangQie() {
				Util.jiangqie();
			}
		}
	}
</script>

<style lang="scss" scoped>
	.main_box {
		padding-bottom: 160rpx;
	}
	
	.jiangqie-block {
		border: none;
	}

	.jiangqie-gust-img,
	.jiangqie-gust-img .image {
		height: 360rpx;
		width: 100%;
	}
</style>
