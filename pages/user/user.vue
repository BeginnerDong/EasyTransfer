<template>
	<view>
		<view class="whiteBj">
			<view class="userHead pdlr4">
				<view class="infor flexColumn">
					<view class="flexCenter"><image class="userPhoto" src="../../static/images/about-img.png" mode=""></image></view>
					<view class="pdt10">快乐的猫</view>
				</view>
			</view>
			
			<view class="mglr4">
				<view class="myRowBetween pdlr4 fs13 radius10 boxShaow">
					<view class="item flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/user-myGold/user-myGold'}})" >
						<view class="ll flex">
							<image class="icon" src="../../static/images/about-icon1.png" mode=""></image>
							<view class="">我的金币</view>
						</view>
						<view class="rr"><image class="arrowR" src="../../static/images/about-icon2.png" mode=""></image></view>
					</view>
					<view class="item flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/user-myFaBu/user-myFaBu'}})" >
						<view class="ll flex">
							<image class="icon" src="../../static/images/about-icon3.png" mode=""></image>
							<view class="">我的发布</view>
						</view>
						<view class="rr"><image class="arrowR" src="../../static/images/about-icon2.png" mode=""></image></view>
					</view>
					<view class="item flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/user-transaction/user-transaction'}})" >
						<view class="ll flex">
							<image class="icon" src="../../static/images/about-icon4.png" mode=""></image>
							<view class="">交易记录</view>
						</view>
						<view class="rr"><image class="arrowR" src="../../static/images/about-icon2.png" mode=""></image></view>
					</view>
					<view class="item flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/user-companyIndex/user-companyIndex'}})" >
						<view class="ll flex">
							<image class="icon" src="../../static/images/about-icon5.png" mode=""></image>
							<view class="">我的企业</view>
						</view>
						<view class="rr"><image class="arrowR" src="../../static/images/about-icon2.png" mode=""></image></view>
					</view>
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
					<image src="../../static/images/nabar4-a.png" />
				</view>
				<view class="text this-text">我的</view>
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
				score:'',
				wx_info:{}
			}
		},
		onLoad() {
			const self = this;
			//self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {


		},
	};
</script>

<style>
	@import "../../assets/style/editInfor.css";
	@import "../../assets/style/navbar.css";
	.userHead{height: 420rpx;background: url(../../static/images/about-icon.png) no-repeat 0 0 /100% auto;}
	.userHead .infor{padding-top: 160rpx;}
	.userPhoto{width: 120rpx;height: 120rpx;border-radius: 50%;display: block;border: 4rpx solid rgba(255,255,255,0.6);}
	
	.myRowBetween .ll .icon{width: 32rpx;height: 32rpx;margin-right: 20rpx;}
	
</style>
