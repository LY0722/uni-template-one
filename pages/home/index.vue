<template>
	<view class="home-wrap">
		<!-- 公告 -->
		<view class="grace-swiper-msg">
			<view class="grace-swiper-msg-icon">
				<text class="iconfont horn-icon">&#xe61e;</text>
			</view>
			<swiper autoplay="true" circular="true" interval="3000">
				<swiper-item>
					<navigator class="grace-content">双十一大促销，1折起，还可以领券领红包叠加</navigator>
				</swiper-item>
				<swiper-item>
					<navigator class="grace-content">双十一大促销，1折起，还可以领券领红包叠加</navigator>
				</swiper-item>
			</swiper>
		</view>
		<!-- 轮播 -->
		<view class="broadcast-wrap">
			<swiper 
				class="broadcast-row"
				:indicator-dots="true" 
				:autoplay="true" 
				:interval="5000" 
				:duration="500">
				<swiper-item v-for="item in itemList" :key="item">
					<image :src="item" class="broadcast-img"></image>
				</swiper-item>
			</swiper>
		</view>
		<!-- 搜索 -->
		<view class="search-wrap">
			<view class="search-row" @click="searchPage()">
				<text class="iconfont search-icon">&#xe614;</text>
				<text class="search-text">搜索</text>
			</view>
		</view>
		<!-- 广告 -->
		<view class="advert-wrap">
			
		</view>
		<!-- 商品列表 -->
		<block>
			<shopp-list :shopList="shoppingList"/>
		</block>
	</view>
</template>

<script>
	import shoppList from '../../components/shoppList/index.vue'
	export default {
		components:{
			shoppList
		},
		data() {
			return {
				itemList: [
					'../../static/broadcast01.jpg',
					'../../static/broadcast02.jpg',
					'../../static/broadcast03.jpg'
				],
				shoppingList: []
			}
		},
		onShow() {
			this.getShopList()
		},
		onReachBottom() {
			this.getShopList()
		},
		methods:{
			searchPage() {
				uni.navigateTo({
					url:"/pages/home/searchShopp/index"
				})
			},
			getShopList(){
				const data = [
					{
						image: 'https://img-cdn-qiniu.dcloud.net.cn/uploads/example/product1.jpg',
						title: 'Apple iPhone X 256GB 深空灰色 移动联通电信4G手机',
						originalPrice: 9999,
						favourPrice: 8888,
						tip: '自营'
					},
					{
						image: 'https://img-cdn-qiniu.dcloud.net.cn/uploads/example/product2.jpg',
						title: 'Apple iPad 平板电脑 2018年新款9.7英寸',
						originalPrice: 3499,
						favourPrice: 3399,
						tip: '优惠'
					},
					{
						image: 'https://img-cdn-qiniu.dcloud.net.cn/uploads/example/product3.jpg',
						title: 'Apple MacBook Pro 13.3英寸笔记本电脑（2017款Core i5处理器/8GB内存/256GB硬盘 MupxT2CH/A）',
						originalPrice: 12999,
						favourPrice: 10688,
						tip: '秒杀'
					},
					{
						image: 'https://img-cdn-qiniu.dcloud.net.cn/uploads/example/product4.jpg',
						title: 'Kindle Paperwhite电纸书阅读器 电子书墨水屏 6英寸wifi 黑色',
						originalPrice: 999,
						favourPrice: 958,
						tip: '秒杀'
					},
					{
						image: 'https://img-cdn-qiniu.dcloud.net.cn/uploads/example/product5.jpg',
						title: '微软（Microsoft）新Surface Pro 二合一平板电脑笔记本 12.3英寸（i5 8G内存 256G存储）',
						originalPrice: 8888,
						favourPrice: 8288,
						tip: '优惠'
					},
					{
						image: 'https://img-cdn-qiniu.dcloud.net.cn/uploads/example/product6.jpg',
						title: 'Apple Watch Series 3智能手表（GPS款 42毫米 深空灰色铝金属表壳 黑色运动型表带 MQL12CH/A）',
						originalPrice: 2899,
						favourPrice: 2799,
						tip: '自营'
					}
				];
				data.forEach((item) => {
					this.shoppingList.push(item)
				})
			}
		}
		
	}
</script>

<style>
	.home-wrap{
		box-sizing: border-box;
		width: 100%;
		min-height: 100vh;
		background: #EFEFEF;
		display: block;
	}
	/* 公告 */
	/* view{display:flex; flex-wrap:wrap; font-size:28upx; height:auto; width:100%;} */
	.horn-icon{
		color: #333;
		line-height: 40upx;
	}
	.grace-content{
		font-size: 25upx;
		color: #666;
		line-height: 40upx;
	}
	.grace-swiper-msg{
		flex-wrap:nowrap;
		padding: 10upx 0 10upx 12upx;
		height: 50upx;
		width:100%;
		background: #FAFAFA;
	}
	.grace-swiper-msg-icon{width:50upx; margin-right:20upx;}
	.grace-swiper-msg-icon image{width:100%; flex-shrink:0;}
	.grace-swiper-msg swiper{width:100%; height:50upx;}
	.grace-swiper-msg swiper-item{line-height:50upx;}
	/* 轮播 */
	.broadcast-wrap{
		display: block;
		width: 100%;
		height: 300upx;
	}
	.broadcast-row{
		height: 300upx;
	}
	.broadcast-img{
		width: 100%;
		height: 300upx;
	}
	/* 搜索 */
	.search-wrap{
		padding: 18upx 20upx;
		width: 100%;
		box-sizing: border-box;
		text-align: center;
	}
	.search-icon{
		font-size: 34upx;
		color: #C8C7CC;
		margin-right: 10upx;
	}
	.search-text{
		font-size: 33upx;
		color: #C8C7CC;
	}
	.search-row{
		height: 70upx;
		line-height: 70upx;
		display: block;
		width: 100%;
		background: #fff;
		border-radius: 5upx;
	}
	/* 商品列表 */
	
</style>