<template>
	<view>
		
		<view class="pdlr4 whiteBj">
			<view class="flex fs13 pdtb10">西安<image class="arrowB" src="../../static/images/home-icon.png" mode=""></image></view>
			<view class="flexRowBetween screenLab color6 pdb15 fs12">
				<view class="ll flex">
					<view class="btn">空壳公司</view>
					<view class="btn">买过社保</view>
					<view class="btn">资产类公司</view>
				</view>
				<view class="flexEnd" @click="Router.navigateTo({route:{path:'/pages/screen/screen'}})"><image class="mgr5" style="width: 24rpx;height: 26rpx;" src="../../static/images/home-icon1.png" mode=""></image>筛选</view>
			</view>
		</view>
		
		
		<view class="fx-fabubtn" @click="Router.navigateTo({route:{path:'/pages/login/login'}})">
			<image class="icon" src="../../static/images/fabu.png" mode=""></image>
		</view>
		
		<view class="pdlr4 companyItems">
			<view class="item pr color6 fs12 mgt15" v-for="(item,index) in companyDate" :key="index"  @click="Router.navigateTo({route:{path:'/pages/companyDetail/companyDetail'}})">
				<view class="FX-Icon">
					<image src="../../static/images/home-icon2.png" mode=""></image>
				</view>
				<view class="pubColor fs13">【编号：79122813】深圳市****教育有限公司</view>
				<view class="text">成立时间：2019-12-19</view>
				<view class="text">注册资本：100万人民币</view>
				<view class="text">实缴资本：0万人民币</view>
				<view class="text">纳税类型：小规模</view>
				<view class="MYiIcon flexCenter">面议</view>
			</view>
		</view>
		
		
		
		<!--底部tab键-->
		<view class="navbar">
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/index/index'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar1-a.png" />
				</view>
				<view class="text this-text">找公司</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/wantBuy/wantBuy'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar2.png" />
				</view>
				<view class="text">求购</view>
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
				companyDate: [{},{},{}]
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
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/companyItems.css";
	
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	
	.screenLab .ll{width: 80%;}
	.screenLab .ll .btn{padding: 0 10rpx;line-height:44rpx;border-radius: 10rpx;border: 1px solid #0fa2e5; text-align: center;margin-right: 20rpx;}
	
	
</style>
