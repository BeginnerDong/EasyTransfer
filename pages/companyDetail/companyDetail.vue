<template>
	<view>
		
		<view class="mglr4 pdtb15">
			<view class="compayTit flex mgb10">
				<view class="icon"><image src="../../static/images/home-icon2.png" mode=""></image></view>
				<view class="text pubColor fs13">【编号：79122813】深圳市****教育有限公司</view>
			</view>
			<view class="flexRowBetween">
				<view class="ll fs12">
					<view >出售价：<text class="fs14 red">面议</text></view>
					<view class="color9 mgt5">更新时间：<text>2019-12-19</text></view>
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
			<view class="flex fs14 ftw"><image class="TitIcon" src="../../static/images/company-details-icon3.png" mode=""></image><text>基本信息</text></view>
			<view class="msgInfor fs12">
				<view class="item">
					<text class="color6">公司名称：</text>
					<text>上海**广告有限公司</text>
				</view>
				<view class="item">
					<text class="color6">注册资本：</text>
					<text>1000万人民币</text>
				</view>
				<view class="item">
					<text class="color6">实缴资本：</text>
					<text>1000万人民币</text>
				</view>
				<view class="item">
					<text class="color6">成立时间：</text>
					<text>2015-03-12</text>
				</view>
				<view class="item">
					<text class="color6">注册地址：</text>
					<text>上海 上海市 杨浦******</text>
				</view>
				<view class="item">
					<text class="color6">经营范围：</text>
					<text>广告设计、制作。代理、发布、灯饰设计、展览展示服务、会议服务、图文设计制作、绿化养护、礼仪服务、动漫设计、计算机软硬件、园林古建筑工程专业施工、建筑装饰建设工程专项设计。</text>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="mglr4 pdtb15">
			<view class="flex fs14 ftw"><image class="TitIcon" src="../../static/images/company-details-icon4.png" mode=""></image><text>税务信息</text></view>
			<view class="msgInfor fs12">
				<view class="item">
					<text class="color6">纳税类型：</text>
					<text>小规模</text>
				</view>
				<view class="item">
					<text class="color6">报税情况：</text>
					<text>正常</text>
				</view>
				<view class="item">
					<text class="color6">申领发票：</text>
					<text>未申领</text>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="mglr4 pdtb15">
			<view class="flex fs14 ftw"><image class="TitIcon" src="../../static/images/company-details-icon5.png" mode=""></image><text>银行信息</text></view>
			<view class="msgInfor fs12">
				<view class="item">
					<text class="color6">银行账户：</text>
					<text>已开票本户</text>
				</view>
				<view class="item">
					<text class="color6">账户是否正常：</text>
					<text>正常</text>
				</view>
				<view class="item">
					<text class="color6">开通网银：</text>
					<text>未开通</text>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="mglr4 pdtb15">
			<view class="flex fs14 ftw"><image class="TitIcon" src="../../static/images/company-details-icon6.png" mode=""></image><text>其他信息</text></view>
			<view class="msgInfor fs12">
				<view class="item">
					<text class="color6">其他信息：</text>
					<text>还有家一般纳税人</text>
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
