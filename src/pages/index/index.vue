<template>
	<view class="index" :style="{overflow:'hidden', height: pageHight}">
		<!-- 搜索 -->
		<search @search = "undataHeight" />
		<!-- 轮播图 -->
		<view class="slider">
			<swiper indicator-dots interval="2000" autoplay indicator-color="rgba(255,255,255,1)" indicator-active-color= "rgba(255, 255, 255, .6)" circular>
				<swiper-item>
					<navigator url=""><image src="/static/uploads/banner1.png"/> </navigator>
				</swiper-item>
				<swiper-item>
					<navigator url=""><image src="/static/uploads/banner2.png"/> </navigator>
				</swiper-item>
				<swiper-item>
					<navigator url=""><image src="/static/uploads/banner3.png"/> </navigator>
				</swiper-item>
			</swiper>
		</view>
		<!-- 功能导航 -->
		<view class="navs">
			<navigator>
				<image src="/static/uploads/icon_index_nav_1@2x.png"/>
			</navigator>
			<navigator>
				<image src="/static/uploads/icon_index_nav_2@2x.png"/>
			</navigator>
			<navigator>
				<image src="/static/uploads/icon_index_nav_3@2x.png"/>
			</navigator>
			<navigator>
				<image src="/static/uploads/icon_index_nav_4@2x.png"/>
			</navigator>
		</view>
		<!-- 楼层 -->
		<view class="floor" v-for="item in 3" :key="item">
			<view class="ftitle">
				<image src="/static/uploads/pic_floor01_title.png" />
			</view>
			<!-- pics -->
			<view class="fitem">
				<navigator url>
				<image src="/static/uploads/pic_floor01_1@2x.png" />
				</navigator>
				<navigator url>
				<image src="/static/uploads/pic_floor01_2@2x.png" />
				</navigator>
				<navigator url>
				<image src="/static/uploads/pic_floor01_3@2x.png" />
				</navigator>
				<navigator url>
				<image src="/static/uploads/pic_floor01_4@2x.png" />
				</navigator>
				<navigator url>
				<image src="/static/uploads/pic_floor01_5@2x.png" />
				</navigator>
			</view>
		</view>
		<!-- 页面底部提示 -->
		<view class="bottom">
			<text>我是有底线的</text>
		</view>
	</view>
</template>

<script>
	import search from "@/components/search"
	export default {
		data() {
			return {
				pageHight: 'auto'
			}
		},
		onLoad() {

		},
		components: {
			search
		},
		methods: {
			undataHeight (data) {
				this.pageHight = data
			}
		}
	}
</script>

<style lang="scss" scoped>
	// 轮播图
	swiper {
		width: 750rpx;
		height: 340rpx;
		navigator {
			display: inline-block;
			width: 750rpx;
			height: 340rpx;
		}
	}
	// 功能导航
	.navs {
		display: flex;
		padding: 30rpx;
		background: #fff;
		justify-content: space-between;
		navigator {
			width: 128rpx;
			height: 140rpx;
		}
	}
	 // 栏目楼层
  .floor {
    .ftitle {
      padding-top: 30rpx;
      background: #f4f4f4;
      image {
        width: 750rpx;
        height: 60rpx;
      }
    }
    // pics
    .fitem {
      padding: 20rpx 16rpx 10rpx;
      overflow: hidden;
      navigator {
        float: left;
        width: 193rpx;
        height: 188rpx;
        margin-left: 10rpx;
        margin-bottom: 10rpx;
      }
      navigator:nth-child(1) {
        width: 232rpx;
        height: 386rpx;
        margin-left: 0;
      }
      navigator:nth-child(2),
      navigator:nth-child(5) {
        width: 273rpx;
        height: 188rpx;
      }
    }
    &:first-child {
      .fitem {
        navigator {
          width: 233rpx;
        }
      }
    }
  }
  .bottom {
	  margin: 30rpx auto;
	  font-size: 24rpx;
	  color: #999;
	  text-align: center;
  }
</style>
