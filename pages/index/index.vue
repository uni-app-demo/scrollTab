<template>
	<view class="content">
		<scroll-view class="scroll-list" scroll-x>
			<view class="tab" v-for="(item, index) in tabs" :key='index' @click.stop='switchTab(index)'>
				<text>{{item.label}} <text>{{item.total}}</text></text>
				<view :class="currentTab == index ? 'line-active' : 'line-inactive'"></view>
			</view>
		</scroll-view>
		
		<view class="item">
			<view :class="[{ active: item.type == 2 }, { errorClass: item.type == 1}]" v-for="(item, index) in data">
				<view class="item-top">
					<text class="num">{{item.num}}</text>
					<text class="label">{{item.label}}</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isActive: false,
				tabs: [{
					label: '全部',
					total: 100
				}, {
					label: '干净房',
					total: 70
				}, {
					label: '在住房',
					total: 28
				}, {
					label: '脏房',
					total: 2
				}, {
					label: '长包房',
					total: 32
				}],
				currentTab: 0,
				data: [{
					num: '802',
					label: '豪华大床房',
					type: 2
				}, {
					num: '802',
					label: '豪华大床房',
					type: 1
				}, {
					num: '802',
					label: '豪华大床房',
					type: 2
				},{
					num: '802',
					label: '豪华大床房',
					type: 2
				},{
					num: '802',
					label: '豪华大床房',
					type: 2
				},{
					num: '802',
					label: '豪华大床房',
					type: 2
				},{
					num: '802',
					label: '豪华大床房',
					type: 2
				}]
			}
		},
		onLoad() {
			
		},
		methods: {
			switchTab (index) {
				this.currentTab = index
			},
		}
	}
</script>

<style>
	.content {
	}
	
	.scroll-list {
		width: 100%;
		white-space: nowrap;
	}
	/deep/.uni-scroll-view ::-webkit-scrollbar {
		 /* 隐藏滚动条，但依旧具备可以滚动的功能 */
		 display: none;
		 width: 0;
		 height: 0;
		 color: transparent;
		 background: transparent;
		}
		/deep/::-webkit-scrollbar {
		 display: none;
		 width: 0;
		 height: 0;
		 color: transparent;
		 background: transparent;
		}
	
	.tab {
		width: 25%;
		height: 80rpx;
		display: inline-flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.line-active {
		width: 25%;
		height: 5rpx;
		background-color: #1E90FF;
	}
	
	.line-inactive {
		width: 20%;
		height: 5rpx;
		background-color: #FFFFFF;
	}
	
	.item {
		width: 100%;
		display: flex;
		flex-wrap: wrap;
	}
	
	.item-top {
		width: 100%;
		height: 50rpx;
		display: flex;
		justify-content: space-between;
	}
	
	.num, .label {
		color: #FFFFFF;
	}
	
	.num {
		width: 20rpx;
		font-size: 25rpx;
	}
	
	.label {
		max-width: 80rpx;
		height: 50rpx;
		font-size: 20rpx;
		white-space: nowrap;
		text-overflow: ellipsis;
		overflow: hidden;
	}
	
	.active {
		width: 125rpx;
		height: 125rpx;
		background-color: #FF0000;
		margin: 20rpx;
	}
	
	.errorClass {
		width: 125rpx;
		height: 125rpx;
		background-color: #1E90FF;
		margin: 20rpx;
	}
</style>
