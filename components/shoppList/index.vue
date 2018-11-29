<template>
	<view class="page">
		<page-head :title="title"></page-head>
		<view class="product-list">
			<view class="product" v-for="(product,index) in shopList" :key="index">
				<view class="image-view">
					<image v-if="renderImage" class="product-image" :src="product.image"></image>
				</view>
				<view class="product-title">{{product.title}}</view>
				<view class="product-price">
					<text class="product-price-favour">￥{{product.originalPrice}}</text>
					<text class="product-price-original">￥{{product.favourPrice}}</text>
					<text class="product-tip">{{product.tip}}</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	props:{
		shopList:{
			type: Array,
			default: []
		}
	},
    data() {
        return {
            title: '商品列表',
            renderImage: true
        };
    },
    methods: {
    }
};
</script>

<style>
.product-list {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    flex-direction: row;
	background: #fff;
}

.product {
    padding: 10upx 20upx;
    display: flex;
    flex-direction: column;
}

.image-view {
    height: 330upx;
    width: 330upx;
}

.product-image {
    height: 330upx;
    width: 330upx;
}

.product-title {
    width: 300upx;
    font-size: 32upx;
    word-break: break-all;
    display: -webkit-box;
    overflow: hidden;
    text-overflow: ellipsis;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
}

.product-price {
    font-size: 28upx;
    position: relative;
}

.product-price-original {
    color: #e80080;
}

.product-price-favour {
    color: #888888;
    text-decoration: line-through;
    margin-left: 10upx;
}

.product-tip {
    position: absolute;
    right: 10upx;
    background-color: #ff3333;
    color: #ffffff;
    padding: 0 10upx;
    border-radius: 5upx;
}
</style>
