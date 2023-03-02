<template>
	<view>
		<view class="tx">
			<uni-row>
				<uni-col :span="6">
					<view class="setCenter" style="height: 80px;border-color: white;">
						<u-avatar :src="src" mode="circle" size="large"></u-avatar>
					</view>
				</uni-col>
				<uni-col :span="18">
					<view style="display:flex;flex-direction:column;justify-content:center;height: 80px;font-size: 15px;padding-left: 5px;color: white;">
						<text>{{username}}</text>
					</view>
				</uni-col>
			</uni-row>
		</view>
		<view class="contains">
			<uni-grid :column="3" :show-border="false" :square="false" @change="change">
				<uni-grid-item v-for="(item ,index) in list" :index="index" :key="index">
					<view class="grid-item-box">
						<text class="text">{{item.badge}}</text>
						<text class="text">{{item.text}}</text>
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>
		<view>
			<u-gap height="30" bg-color="#f9f9f9"></u-gap>
		</view>
		<view style="padding-left: 10px;padding-right: 10px;">
			<u-cell-item :title-style="{'font-size':'10px'}" title="订单信息" :arrow="true"></u-cell-item>
		</view>
		<view class="contains">
			<uni-grid :column="5" :show-border="false" :square="false" @change="change">
				<uni-grid-item v-for="(item ,index) in list1" :index="index" :key="index">
					<view class="grid-item-box">
						<u-icon :name="item.name" size="50"></u-icon>
						<text class="text">{{item.text}}</text>
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>
		<view>
			<u-gap height="30" bg-color="#f9f9f9"></u-gap>
		</view>
		<view style="padding-left: 10px;padding-right: 10px;">
			<u-cell-group>
				<u-cell-item
					icon="red-packet"
					title="我的积分"
					:arrow="true"
				></u-cell-item>
				<u-cell-item
					icon="tags"
					title="砍价"
					:arrow="true"
				></u-cell-item>
				<u-cell-item
					icon="thumb-up"
					title="推荐"
					:arrow="true"
				></u-cell-item>
				<u-cell-item
					icon="setting"
					title="账户设置"
					:arrow="true"
				></u-cell-item>
			</u-cell-group>
		</view>
	</view>
</template>

<script>
	export default {
		name:"avatarPage",
		components:{},
		data() {
			return {
				src:'/static/crab.png',
				username:'Mr.JIANG',
				list: [{
						text: '余额',
						badge: 0,
					},
					{
						text: '积分',
						badge: 0,
					},
					{
						text: '优惠券',
						badge: 0,
					}
				],
				
				list1: [{
						text: '待付款',
						name: 'bag',
					},
					{
						text: '待发货',
						name: 'calendar',
					},
					{
						text: '待收货',
						name: 'car',
					},
					{
						text: '待评价',
						name: 'order',
					},
					{
						text: '退款/售后',
						name: 'file-text',
					}
				]
			}
		},
		onLoad() {
	
		},
		methods: {
			change(e) {
				let {
					index
				} = e.detail

				uni.showToast({
					title: `点击第${index+1}个宫格`,
					icon: 'none'
				})
			},
		}
	}
</script>

<style>
	.tx {
		height: 80px;
		width: 100%;
		background: linear-gradient(to bottom right, #5e5e5e, #333132);
	}
	.grid-item-box {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 5px 0;
	}
	.text {
		font-size: 10px;
		margin-top: 5px;
	}
	
</style>