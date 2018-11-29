<template>
	<view class="container">
		<view class="page-body">
			<scroll-view class="nav-left" scroll-y >
				<view class="nav-left-item" @click="categoryClickMain(item,index)" :key="index" 
					:class="index==categoryActive?'active':''"
				    v-for="(item,index) in categoryList">
					{{item.name}}
				</view>
			</scroll-view>
			<!-- scroll-with-animation -->
			<scroll-view class="nav-right" scroll-y  
				id="scrollDetails"
				:scroll-top="scrollTop" @scroll="scroll">
				<view class="nav-right-row">
					<view :id="index==0?'first':''" class="nav-right-item" v-for="item in subCategoryList" :key="item">
						<view class="right-item-img">
							<image :src="item.LOGO" />
						</view>
						<view class="right-item-shopName">
							<text>{{item.name}}</text>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				categoryList: [
					{id: 1, name: 'T系列'},
					{id: 2, name: 'S系列'},
					{id: 3, name: 'RG系列'},
					{id: 4, name: 'K系列'},
					{id: 5, name: 'XINWEI系列'},
					{id: 6, name: 'M系列'},
					{id: 6, name: 'M系列'},
				],
				subCategoryList: [
					{id: 1, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 2, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 3, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 4, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 5, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 1, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 2, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 3, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 4, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 5, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 1, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 2, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 3, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 4, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 5, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 1, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 2, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 3, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 4, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 5, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
					{id: 6, name: 'T系列', "LOGO": './../../static/intercom1.jpg'},
				],
				height: 0,
				categoryActive: 0,
				scrollTop: 0,
				scrollHeight: 0,
			}
		},
		methods: {
			scroll(e) {
				this.scrollTop = e.detail.scrollTop
			},
			categoryClickMain(item, index) {
				this.scrollTop = 0
				this.categoryActive = index;
				for (let i in this.subCategoryList) {
					this.subCategoryList[i].name = item.name
				}
			},
			getCategory() {
				console.log('页面加载完成')
			}
		}
	}
</script>

<style>
	.page-body {
		display: flex;
		width: 100%;
		background: #fff;
		height: 100vh;
		overflow: hidden;
		box-sizing: border-box;
	}

	.nav-left {
		flex: 0 0 30%;
		background: #EFEFEF;
	}
	
	.nav-left-item {
		height: 100upx;
		border-right: solid 1px #E0E0E0;
		border-bottom: solid 1px #E0E0E0;
		font-size: 30upx;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.nav-right {
		flex: 0 0 70%;
	}
	
	.nav-left ::-webkit-scrollbar{
		width: 0;
		height: 0;
		color: transparent;
	}
	.nav-right ::-webkit-scrollbar{
		width: 0;
		height: 0;
		color: transparent;
	}
	.nav-right-row{
		flex-wrap: wrap;
	}
	
	.nav-right-item {
		flex: 0 0 33%;
		padding: 20upx 0 0 0;
		min-height: 100upx;
		text-align: center;
		font-size: 28upx;
		box-sizing: border-box;
		overflow: hidden;
		flex-direction: column;
	}

	.nav-right-item image {
		width: 100upx;
		height: 100upx;
		/* display: block; */
	}
	.right-item-img{
		display: block;
	}
	.right-item-shopName{
		text-align: center;
		display: block;
	}
	
	.active {
		border-right: none;
		border-left: 6upx solid #FF0972;
		color: #FF0972;
		background: #fff;
	}
</style>