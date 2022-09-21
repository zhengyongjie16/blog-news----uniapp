<template>
  <view class="content">
    <scroll-view class="main_box" scroll-y="true">
      <!-- 首页顶部轮播图 -->
      <view v-if="slides.length > 0" class="jiangqie-swiper">
        <swiper
          indicator-dots="true"
          circular="ture"
          autoplay="autoplay"
          interval="2000"
          duration="duration"
        >
          <swiper-item
            v-for="(slide, index) in slides"
            :key="index"
            @click="clickLink(slide.link)"
          >
            <view>
              <image mode="aspectFill" :src="'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fbkimg.cdn.bcebos.com%2Fpic%2F810a19d8bc3eb135435cb6e6ac1ea8d3fc1f44d7&refer=http%3A%2F%2Fbkimg.cdn.bcebos.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666193773&t=0a84beddc0b6893f27cd8c8eca3539e7'"></image>
            </view>
          </swiper-item>
          <swiper-item
            v-for="(slide, index) in slides"
            :key="index"
            @click="clickLink(slide.link)"
          >
            <view>
              <image mode="aspectFill" :src="'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimages.adsttc.com.qtlcn.com%2Fmedia%2Fimages%2F5bc7%2F9af8%2Ff197%2Fcc6b%2F2200%2F01eb%2Fnewsletter%2FCPT_hero.jpg%3F1539807982&refer=http%3A%2F%2Fimages.adsttc.com.qtlcn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666193805&t=7ff0387b03f54dea1cce0513c95b0578'"></image>
            </view>
          </swiper-item>
        </swiper>
      </view>

      <!-- 自定义图标 -->
      <!-- <view v-if="icon_navs.length>0" class="jiangqie-icon-block">
				<view v-for="(item, index) in icon_navs" :key="index" class="jiangqie-custom-icon" @click="clickLink(item.link)">
					<image mode="aspectFill" :src="item.image"></image>
					<text>{{item.title}}</text>
				</view>
			</view> -->
      <view class="jiangqie-icon-block">
        <view class="jiangqie-custom-icon" @click="clickLink(link.l1)">
          <image
            mode="aspectFill"
            :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/w1.png'"
          ></image>
          <text>源码下载</text>
        </view>
        <view class="jiangqie-custom-icon" @click="clickLink(link.l2)">
          <image
            mode="aspectFill"
            :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/w6.png'"
          ></image>
          <text>官方网站</text>
        </view>
        <view class="jiangqie-custom-icon" @click="clickLink(link.l3)">
          <image
            mode="aspectFill"
            :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/w4.png'"
          ></image>
          <text>个人博客</text>
        </view>
        <view class="jiangqie-custom-icon" @click="clickLink(link.l4)">
          <image
            mode="aspectFill"
            :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/w5.png'"
          ></image>
          <text>联系我们</text>
        </view>
      </view>

      <!-- 简单描述 -->
      <view v-if="about" class="jiangqie-block">
        <view class="jiangqie-head">关于我们</view>
        <view class="jiangqie-simple">
          <p>
            <span style="color: #3366ff"
              ><b style="font-weight:600">来源zhengbbs.cn,基于wordpress的强大的低代码构建</b></span
            >WordPress是使用PHP语言开发的博客平台，用户可以在支持PHP和MySQL数据库的服务器上架设自己的网站。也可以把 WordPress当作一个内容管理系统（CMS）来使用。
          </p>
        </view>
      </view>

      <!-- 滑动展示 -->
      <view
        class="jiangqie-block jiangqie-scroll-block"
      >
        <view class="jiangqie-head">
          最新博客
        </view>
        <scroll-view class="jiangqie-scroll-view" scroll-x="true">
          <view
            @click="clickLink(link.l5)"
          >
            <image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2015/07/17/22/43/student-849822_960_720.jpg'"></image>
            <text>个人简历</text>
          </view>
          <view
            @click="clickLink(link.l6)"
          >
            <image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2016/12/01/18/17/mobile-phone-1875813_960_720.jpg'"></image>
            <text>uni-app微信小程序引入vant weapp</text>
          </view>
          <view
            @click="clickLink(link.l7)"
          >
            <image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2014/08/05/10/30/iphone-410324_960_720.jpg'"></image>
            <text>Vue面包屑导航实现方案</text>
          </view>
          <view
            @click="clickLink(link.l8)"
          >
            <image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2018/05/01/13/04/miniature-3365503_960_720.jpg'"></image>
            <text>使用 WordPress 应用镜像搭建网站</text>
          </view>
        </scroll-view>
      </view>

      <view
        class="jiangqie-block"
      >
        <view class="jiangqie-head">
          其他动态
          <text @click="clickNewsMore()">查看更多</text>
        </view>
        <!-- 列表内容块 - 左图 -->
        <view
          class="jiangqie-list-side"
          @click="clickLink('https://liubing.me/google-mirror.html')"
        >
          <view class="jiangqie-list-img">
            <image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2015/02/02/15/28/bar-621033_960_720.jpg'"></image>
          </view>
          <view class="jiangqie-list-text">
            <view class="jiangqie-list-title">分享几个可用的谷歌镜像</view>
            <view class="jiangqie-list-data">
              <text>浏览 329</text>
              <text>2022-4-22</text>
            </view>
          </view>
        </view>
        <view
          class="jiangqie-list-side"
          @click="clickLink('https://liubing.me/uni-app-lb-picker.html')"
        >
          <view class="jiangqie-list-img">
            <image mode="aspectFill" :src="'https://cdn.pixabay.com/photo/2016/04/14/07/56/icon-1328421_960_720.jpg'"></image>
          </view>
          <view class="jiangqie-list-text">
            <view class="jiangqie-list-title">uniapp lb-picker选择器</view>
            <view class="jiangqie-list-data">
              <text>浏览 62</text>
              <text>2022-1-04</text>
            </view>
          </view>
        </view>
        <view
          class="jiangqie-list-side"
          @click="clickLink('https://liubing.me/wordpress-all-static-cdn.html')"
        >
          <view class="jiangqie-list-img">
            <image mode="aspectFill" :src="'https://img0.baidu.com/it/u=1358779379,2958771478&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=312'"></image>
          </view>
          <view class="jiangqie-list-text">
            <view class="jiangqie-list-title">wordpress优化，整站资源CDN处理</view>
            <view class="jiangqie-list-data">
              <text>浏览 198</text>
              <text>2021-9-12</text>
            </view>
          </view>
        </view>
        <view
          class="jiangqie-list-side"
          @click="clickLink('https://liubing.me/recommend-several-free-unlimited-cdns.html')"
        >
          <view class="jiangqie-list-img">
            <image mode="aspectFill" :src="'https://img1.baidu.com/it/u=1648885844,2590868475&fm=253&fmt=auto&app=138&f=JPG?w=500&h=333'"></image>
          </view>
          <view class="jiangqie-list-text">
            <view class="jiangqie-list-title">推荐几款免费且不限流量的全球CDN</view>
            <view class="jiangqie-list-data">
              <text>浏览 77</text>
              <text>2021-8-22</text>
            </view>
          </view>
        </view>
      </view>

      <!-- 留言表单 -->
      <view v-if="feedback" class="jiangqie-block">
				<view class="jiangqie-head">{{feedback.title}}</view>
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
					<view class="jiangqie-base-block jiangqie-form-btn">
						<view class="jiangqie-button" @click="clickSubmit()">提交</view>
					</view>
				</view>
			</view>

      <!-- 合作伙伴 -->
      <view
        v-if="friends.length > 0"
        class="jiangqie-block jiangqie-cooperate-block"
      >
        <view class="jiangqie-head"> 合作伙伴 </view>
        <view class="jiangqie-cooperate">
          <scroll-view class="jiangqie-scroll-cooperate" scroll-x="true">
            <view
            >
              <image mode="aspectFill" :src="'https://img1.baidu.com/it/u=2433155157,2652367159&fm=253&fmt=auto&app=138&f=JPEG?w=750&h=300'"></image>
            </view>
            <view
            >
              <image mode="aspectFill" :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/2.png'"></image>
            </view>
            <view
            >
              <image mode="aspectFill" :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/5.png'"></image>
            </view>
            <view
            >
              <image mode="aspectFill" :src="'https://ow.jiangqie.com/wp-content/uploads/2021/05/3.png'"></image>
            </view>
          </scroll-view>
        </view>
      </view>

      <!-- 悬浮菜单 -->
      <view class="jiangqie-float-block">
        <view v-if="phone_switch" @click="clickPhone()">电话</view>
        <!-- #ifdef MP-WEIXIN -->
        <button class="button" v-if="contact_switch" open-type="contact">
          <view>客服</view>
        </button>
        <!-- #endif -->
        <view v-if="feedback_switch" @click="clickFeedback()">反馈</view>
      </view>

      <view @click="clickJiangQie" class="jiangqie-block jiangqie-brand"
        >由 zhengbbs.cn 提供技术支持 备案编号：</view
      >
    </scroll-view>
  </view>
</template>

<script>

import Util from "@/utils/util";
import Alert from "@/utils/alert";
import Api from "@/utils/api";
import Rest from "@/utils/rest";

export default {
  data() {
    this.load = false;

    return {
	  link:{
		l1:"https://github.com/zhengyongjie16",
		l2:"http://43.138.251.116",
		l3:"http://43.138.251.116/%e5%8d%9a%e5%ae%a2",
		l4:"http://43.138.251.116/%e8%81%94%e7%b3%bb",
    //BLOG
    l5:"http://43.138.251.116/unlistone/56.html",
    l6:"http://43.138.251.116/unlistone/64.html",
    l7:"http://43.138.251.116/unlistone/61.html",
    l8:"http://43.138.251.116/unlistone/76.html"
	},
      slides: [],
      icon_navs: [],
      about: undefined,
      goods_list: undefined,
      news_list: undefined,
      feedback: undefined,
      friends: [],

      username: "",
      phone: "",
      email: "",
      content: "",

      phone_switch: 0,
      phone_number: "",
      contact_switch: 0,
      feedback_switch: 0,
    };
  },

  methods: {
    jqOnLoad() {
      Rest.post(Api.JQ_OW_FREE_SETTING_HOME, {}).then(
        (res) => {
          console.log('res',res.data.friends)
          getApp().globalData.appName = res.data.title;
          getApp().globalData.appDesc = res.data.keywords;
          getApp().globalData.appKeyword = res.data.desc;
          // #ifdef MP-BAIDU
          swan.setPageInfo({
            title: getApp().globalData.appName,
            description: getApp().globalData.appDesc,
            keywords: getApp().globalData.appKeyword,
          });
          // #endif

          if (res.data.thumb) {
            getApp().globalData.appThumb = res.data.thumb;
          }

          uni.setNavigationBarTitle({
            //title: getApp().globalData.appName
            title: "南圣安地列斯",
          });

          uni.setNavigationBarColor({
            frontColor: "#000000",
            backgroundColor: "#33CCFF",
          });

          this.slides = res.data.slides;
          this.icon_navs = res.data.icon_navs;
          this.about = res.data.about;
          this.goods_list = res.data.goods_list;
          this.news_list = res.data.news_list;
          this.feedback = res.data.feedback;
          this.friends = res.data.friends;

          this.phone_switch = res.data.phone_switch;
          this.phone_number = res.data.phone_number;
          this.contact_switch = res.data.contact_switch;
          this.feedback_switch = res.data.feedback_switch;
        },
        (err) => {
          console.log(err);
        }
      );
    },

    jqOnShow() {
      if (!this.load) {
        this.load = true;
        this.jqOnLoad();
      }
    },

    clickLink(link) {
      Util.openLink(link);
    },

    clickPost(post_id) {
      Util.openLink("/pages/detail/detail?post_id=" + post_id);
    },

    clickNewsMore() {
      Util.openLink("/pages/list/list");
    },

    clickSubmit() {
      Rest.post(Api.JQ_OW_FREE_USER_FEEDBACK, {
        username: this.username,
        phone: this.phone,
        email: this.email,
        content: this.content,
      }).then((res) => {
        if (res.code == 0) {
          Alert.success("留言成功");
          this.username = "";
          this.phone = "";
          this.email = "";
          this.content = "";
        } else {
          Alert.error(res.msg);
        }
      });
    },

    clickPhone() {
      uni.makePhoneCall({
        phoneNumber: "15277018586",
      });
    },

    clickFeedback() {
      uni.$emit("feedback", {});
    },

    clickJiangQie() {
      Util.jiangqie();
    },
  },
};
</script>

<style lang="scss" scoped>
.main_box {
  padding-bottom: 160rpx;
}

.jiangqie-icon-block {
  display: flex;
  justify-content: space-around;
}

.jiangqie-float-block {
  .button {
    display: inline;
    margin: 0;
    padding: 0;
    background-color: rgba(255, 255, 255, 0);
  }
}
</style>
