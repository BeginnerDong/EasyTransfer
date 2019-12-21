<template>
	<view>
		
		<view class="myRowBetween">
			<view class="item flexRowBetween fs13">
				<view class="ll">总金额：</view>
				<view class="rr flexEnd red">￥20000</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">首次付款：</view>
				<view class="rr flexEnd red">￥10000</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">尾款：</view>
				<view class="rr flexEnd red">￥10000</view>
			</view>
		</view>
		
		<view class="submitbtn" style="margin-top: 200rpx;">
			<button class="btn" type="button">托管转让金</button>
		</view>
		
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				wx_info:{},
				is_show:false,
				num:false
			}
		},
		
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			getMainData() {
				const self = this;
				console.log('852369')
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				self.$apis.orderGet(postData, callback);
			}
		}
	};
</script>

<style>
	@import "../../assets/style/editInfor.css";
	
	page{padding-bottom: 190rpx;}
	.myRowBetween .item{padding: 30rpx 4%;}
</style>
