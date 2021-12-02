<template>
	<view>
		<!-- swiper -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="item in swiper" :key="item.goods_id">
				<image :src="item.image_src" class="swiper-img"></image>
			</swiper-item>
		</swiper>
		<!-- nav -->
		<view class="nav">
			<view class="nav-item" v-for="item in nav">
				<view class="iconfont" v-html="item.icon"></view>
				<text>{{item.text}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swiper: [],
				nav: {
					nav1: {
						text: '黑马超市',
						icon: '&#xe60d;'
					},
					nav2: {
						text: '联系我们',
						icon: '&#xe608;'
					},
					nav3: {
						text: '社区图片',
						icon: '&#xe650;'
					},
					nav4: {
						text: '学习视频',
						icon: '&#xf0024;'
					},
				}
			}
		},
		onLoad() {
			this.getswiper()
		},
		methods: {
			getswiper() {
				uni.request({
					method: "GET",
					url: "https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata",
					success: (res) => {
						console.log(res.data)
						this.swiper = res.data.message
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	swiper {
		height: 380rpx;

		.swiper-img {
			width: 100%;
			height: 100%;
		}
	}

	.nav {
		display: flex;
		padding-bottom: 30rpx;
		border-bottom: 5rpx solid #eeeeee;

		.nav-item {
			display: flex;
			flex-direction: column;
			align-items: center;
			flex: 1;

			.iconfont {
				width: 100rpx;
				height: 100rpx;
				line-height: 100rpx;
				margin: 20rpx 0;
				text-align: center;
				font-family: "iconfont" !important;
				border-radius: 50%;
				background-color: #c51e00;
				font-size: 40rpx;
				color: #FFFFFF;
				font-style: normal;
				-webkit-font-smoothing: antialiased;
				-moz-osx-font-smoothing: grayscale;
			}
		}
	}
</style>
