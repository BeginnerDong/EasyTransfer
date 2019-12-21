<template>
	<view>
		
		<view class="mglr4 pdtb15">
			<view class="flexRowBetween">
				<view class="ll" style="width: 75%;">
					<view class="pubColor fs13">急收香港贸易公司</view>
					<view class="color9 mgt5 fs12">更新时间：<text>2019-12-19</text></view>
				</view>
				<view class="">
					<view class="flexEnd fs12 color9"><image class="shareIcon mgr5" src="../../static/images/company-details-icon1.png" mode=""></image>分享</view>
					<view class="fs10 red mgt5">分享金￥5</view>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="compayUser mglr4 pdtb15 flexRowBetween">
			<view class="ll flex fs12">
				<image class="photo" src="../../static/images/company-details-img.png" mode=""></image>
				<view class="fabuName">
					<view>发布人：<text>王小姐</text></view>
					<view class="color6">用户</view>
				</view>
			</view>
			<view class="rr flexEnd pubColor fs12" @click="tel">
				<image style="width: 34rpx;height: 36rpx;margin-right: 10rpx;" src="../../static/images/company-details-icon2.png" mode=""></image>
				<text>15623455454</text>
			</view>
		</view>
		<view class="f5H5"></view>
		<view class="mglr4 pdtb15">
			<view class="flex fs14 ftw"><image class="TitIcon" src="../../static/images/company-details-icon7.1.png" mode=""></image><text>求购信息</text></view>
			<view class="msgInfor fs12">
				<view class="item flex">
					<text class="color6">预算费用：</text>
					<view class=""><text class="red mgr5">1200万</text>人民币</view>
				</view>
				<view class="item">
					<text class="color6">求购区域：</text>
					<text>全国</text>
				</view>
				<view class="item">
					<text class="color6">求购描述：</text>
					<text>业务需要急收几家香港贸易类型的空壳公司,有闲置香港公司想转让的可以联系我,微信同号</text>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="mglr4 pdtb15">
			<view class="flex fs14 ftw"><image class="TitIcon" src="../../static/images/company-details-icon7.png" mode=""></image><text>悬赏信息</text></view>
			<view class="msgInfor fs12">
				<view class="item">
					<text class="color6">悬赏信息：</text>
					<text>分享一次可得10金币(只有三个名额哟~)</text>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="submitbtn fx-subBtn pdtb15 whiteBj boxShaow">
			<button class="btn" type="button" @click="Router.navigateTo({route:{path:'/pages/companyDetail-orderMsg/companyDetail-orderMsg'}})">发起交易</button>
			<view class="agreeSel pdt5 fs12 color9 flex">
				<view class="selt mgr5" @click="agrren"><image class="icon" :src="num==true?'../../static/images/company-details-icon9.png':'../../static/images/company-details-icon8.png'" mode=""></image></view>
				<view @click="xuzhiShow">交易须知</view>
			</view>
		</view>
		
		<view class="xieyiAlert" v-show="is_xuzhiShow">
			<view class="infor">
				<view class="closeBtn" style="top: auto;bottom: 30rpx;"  @click="xuzhiShow">×</view>
				<view class="center fs14 pdb10">交易须知</view>
				<view class="cont fs12">
					<view>1、个人粉色发挥二十五后覅二姑夫规划局咖啡店是逻辑回归公交卡廊坊市开了个会；</view>
					<view>2、公交卡发生过了人生观估计快了发的是赶快来发过来好几个粉红色的洛凯股份股份深加工和发的是来了个；</view>
					<view>3、股份的股份上来看家给开发商老大哥就感觉分离的金盾股份了解公司和过分的话刚发的刚发的刚发的赛挂电话通过话的他回个话超凡大师；</view>
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
				wx_info:{},
				is_show:false,
				num:false,
				is_xuzhiShow:false
			}
		},
		
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			agrren(){
				const self = this;
				self.num = !self.num
			},
			xuzhiShow(){
				const self = this;
				self.is_xuzhiShow = !self.is_xuzhiShow
			},
			tel(){
				wx.makePhoneCall({
					phoneNumber: '15623455454',
				})
			},
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
	@import "../../assets/style/companyDetail.css";
	@import "../../assets/style/xieyiAlert.css";
	
	page{padding-bottom: 190rpx;}
	
</style>
