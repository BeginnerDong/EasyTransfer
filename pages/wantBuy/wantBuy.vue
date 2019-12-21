<template>
	<view>
		
		<view class="threeAddress pdtb10 fs13 whiteBj flexRowBetween">
			<view class="child flexCenter">
				<text>省</text>
				<image class="arrowB" src="../../static/images/home-icon.png" mode=""></image>
			</view>
			<view class="child flexCenter">
				<text>市</text>
				<image class="arrowB" src="../../static/images/home-icon.png" mode=""></image>
			</view>
			<view class="child flexCenter">
				<text>区</text>
				<image class="arrowB" src="../../static/images/home-icon.png" mode=""></image>
			</view>
		</view>
		
		<view class="fx-fabubtn" @click="Router.navigateTo({route:{path:'/pages/wantBuy-buy/wantBuy-buy'}})">
			<image class="icon" src="../../static/images/fabu.png" mode=""></image>
		</view>
		
		<view class="pdlr4 companyItems wantButs">
			<view class="item fs12 mgt15 flexRowBetween" v-for="(item,index) in wantBuyDate" :key="index"  >
				<view class="ll color6" @click="Router.navigateTo({route:{path:'/pages/wantBuyDetail/wantBuyDetail'}})">
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
		
		
		
		<!--底部tab键-->
		<view class="navbar">
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/index/index'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar1.png" />
				</view>
				<view class="text">找公司</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/wantBuy/wantBuy'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar2-a.png" />
				</view>
				<view class="text this-text">求购</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/serviceDaTing/serviceDaTing'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar3.png" />
				</view>
				<view class="text">服务大厅</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/user/user'}})" >
				<view class="nav_img">
					<image src="../../static/images/nabar4.png" />
				</view>
				<view class="text">我的</view>
			</view>
		</view>
		<!--底部tab键 end-->
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
				wantBuyDate: [{},{},{}]
			}
		},
		
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
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
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/companyItems.css";
	
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	.threeAddress .child{width: 33.3%;}
	
</style>
