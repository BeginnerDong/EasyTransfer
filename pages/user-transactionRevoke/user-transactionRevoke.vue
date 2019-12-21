<template>
	<view>
		
		<view class="mglr4">
			<view class="myRowBetween whiteBj radius10 boxShaow mgt15">
				<view class="item flexRowBetween fs13 color6">
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
			<view class="pdt30 pdb15 borderB1 flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/serviceDaTingDetail/serviceDaTingDetail'}})">
				<view>订单详情</view>
				<view><image class="arrowR" src="../../static/images/about-icon2.png" mode=""></image></view>
			</view>
			<view class="mgt20 mgb10">撤销理由</view>
			<view>
				<textarea class="f5bj" value="" placeholder="请输入撤销订单的原因" />
			</view>
			
		</view>	
			<view class="submitbtn" style="margin-top: 160rpx;">
				<button class="btn" type="button">确定</button>
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
	
	.myRowBetween .item{padding: 30rpx 4%;}
</style>
