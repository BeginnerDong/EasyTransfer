<template>
	<view>
		
		<view class="mglr4 pdtb15">
			<view class="pubColor fs13">广州专业10年注册公司记账报税</view>
			<view class="flexRowBetween">
				<view class="color9 mgt5 fs12">更新时间：<text>2019-12-19</text></view>
				<view class="flexEnd fs12 color9"><image class="shareIcon mgr5" src="../../static/images/company-details-icon1.png" mode=""></image>分享</view>
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
			<view class="msgInfor fs12">
				<view class="item flex">
					<text class="color6">服务区域：</text>
					<text>广东 广东市</text>
				</view>
				<view class="item">
					<text class="color6">代办项目：</text>
					<text>股权变更 | 执照加快 | 代领发票 | 公司买卖 | 商标过户 | 专利过户 | 疑难核名 | 工商疑难处理 | 发票增量 | 资质代办 | 尽业调查</text>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		<view class="mglr4 pdtb15">
			<view class="ftw mgb10">更多服务</view>
			<view class="color6 fs12 xqInfor">
				<view class="">广州财务公司已经有多年的注册经验，已为500余家注册，为企业代理注册公司我们本职“客户至上、信誉保障”的服务宗旨，竭诚为广大客户服务，公司拥有一支作风过硬、训练有素的专业团队，汇集一批专业性强、技术性强的会计师、注册会计师、注册税务师等为各种企业运作中提供工商、税务、知识产权等一系列服务。注册公司您需要准备的材料（内资）：</view>
				<view>1.公司名称 2.经营范围 3.注册资本 4.注册地址 5.法人及股东6.法人及股东优盾（或者数字证书）。</view>
				<view class="">（二）代理注册服务内容</view>
				<view>1、免费工商局核名；</view>
				<view>2、免费准备注册登记材料；</view>
				<view>3、免费工商局交材料，领取执照；</view>
				<view>4、刻章、印章备案；</view>
				<view>（三）其它工商代办服务</view>
				<view>1、公司转让：科技公司，建筑公司，贸易公司，网络公司等小规模公司</view>
				<view>2、工商注册：有限公司、个人独资企业、集体所有制等各类企业、研究院的新设立。</view>
				<view>3、疑难加急：税务疑难问题、工商疑难问题、加急交件、加急出照。</view>
				<view>4、代理记账：代理记账 、银行开户、申请税控、税控机托管等服务。</view>
				<view>5、提供集中办公区注册地址：可以申请税控，会议室，工商合法的注册地址。如果你的实际经营地址不能注册，就可以在集中办公区注册执照。</view>
				<view>6、工商、税务等证件变更：变更法人、变更公司名称、变更地址、变更经营范围、变更股权等一系统证照变更服务。</view>
				<view>7、专项审批：食品流通、进出口权、商标注册；</view>
				<view>8、社保公积金：社保开户、增减员，公积金开户、增减员等；</view>
				<view>9、代办各类资质审批（一般纳税人、食品流通、进出口、高新技术企业）；</view>
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
	
	page{padding-bottom: 60rpx;}
	.xqInfor view{margin-bottom: 20rpx;}
</style>
