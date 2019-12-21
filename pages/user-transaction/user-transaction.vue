<template>
	<view>
		<view class="orderNav pdlr4 flexRowBetween whiteBj">
			<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">购买的</view>
			<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">卖出的</view>
		</view>
		
		<view class="mglr4">
			<view class="tingLis" v-show="curr==1">
				<view class="item radius10 boxShaow pr">
					<image class="banIcon" src="../../static/images/transaction-records-icon.png" mode=""></image>
					<view class="flexRowBetween fs12">
						<view class="color9 mgl10">交易时间：2019.12.19</view>
						<view class="red">首付款已付</view>
					</view>
					<view class="flexRowBetween pdt10 pdb15">
						<view class="ll">
							<image class="pic" src="../../static/images/service-img.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="fs13">公司民称名称</view>
							<view class="fs10 color9">资质代办</view>
							<view class="flex fs12 color6">
								<image class="s-icon" src="../../static/images/service-icon2.png" mode=""></image>
								<text>广东 深圳市</text>
							</view>
							<view class="flex fs12">
								<image class="s-icon" src="../../static/images/service-icon3.png" mode=""></image>
								<text>18659235656</text>
							</view>
							
						</view>
					</view>
					<view class="flexEnd fs12 color6">
						<view class="Bbtn">支付尾款</view>
						<view class="Bbtn" @click="Router.navigateTo({route:{path:'/pages/user-transactionRevoke/user-transactionRevoke'}})">撤销交易</view>
					</view>
				</view>
				<view class="item radius10 boxShaow pr">
					<image class="banIcon" src="../../static/images/transaction-records-icon.png" mode=""></image>
					<view class="flexRowBetween fs12">
						<view class="color9 mgl10">交易时间：2019.12.19</view>
						<view class="red">全款已付</view>
					</view>
					<view class="flexRowBetween pdt10 pdb15">
						<view class="ll">
							<image class="pic" src="../../static/images/service-img.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="fs13">公司民称名称</view>
							<view class="fs10 color9">资质代办</view>
							<view class="flex fs12 color6">
								<image class="s-icon" src="../../static/images/service-icon2.png" mode=""></image>
								<text>广东 深圳市</text>
							</view>
							<view class="flex fs12">
								<image class="s-icon" src="../../static/images/service-icon3.png" mode=""></image>
								<text>18659235656</text>
							</view>
							
						</view>
					</view>
				</view>
			</view>
			<view class="tingLis" v-show="curr==2">
				<view class="item radius10 boxShaow pr">
					<image class="banIcon" src="../../static/images/transaction-records-icon.png" mode=""></image>
					<view class="flexRowBetween fs12">
						<view class="color9 mgl10">交易时间：2019.12.19</view>
						<view class="red">首付款已付</view>
					</view>
					<view class="flexRowBetween pdt10 pdb15">
						<view class="ll">
							<image class="pic" src="../../static/images/service-img.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="fs13">公司民称名称</view>
							<view class="fs10 color9">资质代办</view>
							<view class="flex fs12 color6">
								<image class="s-icon" src="../../static/images/service-icon2.png" mode=""></image>
								<text>广东 深圳市</text>
							</view>
							<view class="flex fs12">
								<image class="s-icon" src="../../static/images/service-icon3.png" mode=""></image>
								<text>18659235656</text>
							</view>
							
						</view>
					</view>
					<view class="flexEnd fs12 color6">
						<view class="Bbtn"  @click="Router.navigateTo({route:{path:'/pages/user-transactionRevoke/user-transactionRevoke'}})">撤销交易</view>
					</view>
				</view>
				<view class="item radius10 boxShaow pr">
					<image class="banIcon" src="../../static/images/transaction-records-icon.png" mode=""></image>
					<view class="flexRowBetween fs12">
						<view class="color9 mgl10">交易时间：2019.12.19</view>
						<view class="red">全款已付</view>
					</view>
					<view class="flexRowBetween pdt10 pdb15">
						<view class="ll">
							<image class="pic" src="../../static/images/service-img.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="fs13">公司民称名称</view>
							<view class="fs10 color9">资质代办</view>
							<view class="flex fs12 color6">
								<image class="s-icon" src="../../static/images/service-icon2.png" mode=""></image>
								<text>广东 深圳市</text>
							</view>
							<view class="flex fs12">
								<image class="s-icon" src="../../static/images/service-icon3.png" mode=""></image>
								<text>18659235656</text>
							</view>
							
						</view>
					</view>
				</view>
			</view>
			
		</view>
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				score:'',
				wx_info:{},
				curr:1
			}
		},
		onLoad() {
			const self = this;
			//self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeCurr(curr){
				const self = this;
				if(curr!=self.curr){
					self.curr = curr
				}
			}

		},
	};
</script>

<style>
	@import "../../assets/style/orderNav.css";
	@import "../../assets/style/tingLis.css";
	
	page{background: #F5F5F5;}
	.orderNav .tt{width: 50%;}
	.tingLis .item{padding: 10rpx 4% 30rpx 4%;}
	.banIcon{width: 40rpx;height: 50rpx;display: block;position: absolute; top: 0;left: 0;}
</style>
