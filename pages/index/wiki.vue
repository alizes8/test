<template>
	<uni-search-bar :style="{backgroundColor:bgcolor}" @confirm="search" cancel-button="none" :focus="true"
		v-model="searchValue">
	</uni-search-bar>
	<view class="catogory">
		<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" :show-scrollbar="true">
					<view v-for="(item,index) in articleCats" class="scroll-view-item_H"
					 :class="cur == index ? 'cur-item' : ''"
					 @click="moveIndex(index)">{{ item.catName }}</view>
				</scroll-view>
		<uni-icons :type="type" class="more"></uni-icons>
	</view>

</template>

<script>
	import { getRequest } from '@/http/index.js'
	export default {
		data() {
			return {
				searchValue: '',
				bgcolor: '#00aaff',
				frontColor: '#ffffff',
				type: 'bottom',
				articleCats:[],
				cur:0
			}
		},
		onLoad() {
			//导航栏背景
			uni.setNavigationBarColor({
				backgroundColor: this.bgcolor,
				frontColor: this.fontColor
			})
			this.init();
			
		},

		methods: {
			init(){
				getRequest('api/articleCat/all')
				.then(res => {
					const articleCats = res.data.articleCats;
					this.articleCats.push({})
					articleCats.forEach(item => {
						if(item.catName != '推荐')
							this.articleCats.push(item);
						else
							this.articleCats[0] = item;
					})
					
				}).catch(err => {
					console.error(err);
				})
			},
			moveIndex(i){
				this.cur = i;
				const cateId = this.articleCats[i].id;
				getRequest(`api/article/${cateId}`)
			},
			search(e) {
				console.log(e)
			},
			scroll(e) {
				// console.log(e)
			}
		}
	}
</script>

<style>
	.catogory {
		position: relative;

	}

	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
		height: 60rpx;
		border-bottom: 1upx solid #ccc;
	}
	/deep/::-webkit-scrollbar{
		display: none;
		width: 0;
		height: 0;
	}


	.scroll-view-item_H {
		display: inline-block;
		width: 100upx;
		line-height: 60rpx;
		text-align: center;
		font-size: 16rpx;
	

	}

	.more {
		position: absolute;
		top: 10upx;
		right: 0;
		background-color: #f5f5f5;
	}
</style>