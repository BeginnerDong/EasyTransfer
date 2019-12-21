<template>
	<view>
		<view class="orderNav pdlr4 flexRowBetween whiteBj">
			<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">我要买</view>
			<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">我要卖</view>
			<view class="tt" :class="curr==3?'on':''" @click="changeCurr('3')">我能办</view>
		</view>
		
		<view class="mglr4">
			<view class="companyItems" v-show="curr==1">
				<view class="item pr color6 fs12 mgt15" v-for="(item,index) in companyDate" :key="index"  @click="Router.navigateTo({route:{path:'/pages/companyDetail/companyDetail'}})">
					<view class="FX-Icon">
						<image src="../../static/images/home-icon2.png" mode=""></image>
					</view>
					<view class="pubColor fs13">【编号：79122813】深圳市****教育有限公司</view>
					<view class="text">成立时间：2019-12-19</view>
					<view class="text">注册资本：100万人民币</view>
					<view class="text">实缴资本：0万人民币</view>
					<view class="text">纳税类型：小规模</view>
					<view class="MYiIcon flexCenter">￥2000</view>
				</view>
			</view>
			
			<view class="companyItems wantButs"  v-show="curr==2">
				<view class="item fs12 mgt15 flexRowBetween" v-for="(item,index) in wantBuyDate" :key="index"  @click="Router.navigateTo({route:{path:'/pages/wantBuyDetail/wantBuyDetail'}})">
					<view class="ll color6">
						<view class="pubColor fs13">求购一家上海各区的公司</view>
						<view class="text">发布时间：2019-12-19</view>
						<view class="text">求购区域：上海</view>
						<view class="text">预算费用：0万人民币</view>
						<view class="text">发布人：小凡</view>
					</view>
					<view class="rr flexColumn" @click="tel">
						<image class="phoneIcon" src="../../static/images/qiugou-icon1.png" mode=""></image>
						<view class="phoneNum">15685623568</view>
					</view>
				</view>
			</view>
			
			<view class="tingLis" v-show="curr==3">
				<view class="item radius10 boxShaow pr flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/serviceDaTingDetail/serviceDaTingDetail'}})">
					<view class="ll">
						<image class="pic" src="../../static/images/service-img.png" mode=""></image>
					</view>
					<view class="rr">
						<view class="fs13">公司民称名称</view>
						<view class="fs10 color9">资质代办 | </view>
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
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				score:'',
				wx_info:{},
				curr:1,
				companyDate:[{},{}],
				wantBuyDate:[{},{}]
			}
		},
		onLoad() {
			const self = this;
			//self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			tel(){
				wx.makePhoneCall({
					phoneNumber: '15623455454',
				})
			},
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
	@import "../../assets/style/companyItems.css";
	@import "../../assets/style/tingLis.css";
	
	page{background: #F5F5F5;}
	.orderNav .tt{width: 33.3%;}
</style>
