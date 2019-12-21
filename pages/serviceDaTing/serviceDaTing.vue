<template>
	<view>
		
		<view class="pdlr4 pdt15 pdb15 whiteBj fs13">
			<view class="flexRowBetween">
				<view class="selt-L">服务区域：</view>
				<view class="selt-R flex">
					<view class="adrs flexRowBetween">
						<text class="text">省</text>
						<image class="arrIcon" src="../../static/images/add-icon2.png" mode=""></image>
					</view>
					<view class="adrs flexRowBetween">
						<text class="text">市</text>
						<image class="arrIcon" src="../../static/images/add-icon2.png" mode=""></image>
					</view>
					<view class="adrs flexRowBetween">
						<text class="text">区</text>
						<image class="arrIcon" src="../../static/images/add-icon2.png" mode=""></image>
					</view>
				</view>
			</view>
			<view class="flexRowBetween pdt15">
				<view class="selt-L">服务项目：</view>
				<view class="selt-R flexRowBetween">
					<view class="color6">股权变更</view>
					<view class="flexEnd color6" @click="drawerShow"><image class="mgr5" style="width: 24rpx;height: 26rpx;" src="../../static/images/home-icon1.png" mode=""></image>筛选</view>
				</view>
			</view>
		</view>
		
		<view class="fx-fabubtn" @click="Router.navigateTo({route:{path:'/pages/serviceDaTing-apply/serviceDaTing-apply'}})">
			<image class="icon" src="../../static/images/fabu.png" mode=""></image>
		</view>
		
		<view class="mglr4">
			<view class="tingLis">
				<view class="item radius10 boxShaow pr flexRowBetween" v-for="(item,index) in tingLisDate" :key="index" @click="Router.navigateTo({route:{path:'/pages/serviceDaTingDetail/serviceDaTingDetail'}})">
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
		
		<view class="black-bj" v-show="is_show"></view>
		<view class="drawerBox" :class="is_show==true?'move':''">
			<view class="color6 fs14 pdb15">服务项目</view>
			<view class="items center flex fs13">
				<view class="btn" :class="{on:item.check}" @click="checkbox(index)" v-for="(item,index) in serviceClass" :key="index">{{item.title}}</view>
			</view>
			<view class="submitbtn" style="margin-top: 200rpx;">
				<button class="btn" type="button"  @click="drawerShow">确定</button>
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
					<image src="../../static/images/nabar3-a.png" />
				</view>
				<view class="text this-text">服务大厅</view>
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
				tingLisDate:[{},{},{},{},{}],
				serviceClass:[
					{title:'股权变更',check:true},
					{title:'公司买卖',check:false},
					{title:'代理记账',check:false},
					{title:'资质代办',check:false},
					{title:'商标过户',check:false},
					{title:'专利过户',check:false},
					{title:'挂靠地址',check:false},
					{title:'执照加快',check:false},
					{title:'代领发票',check:false},
					{title:'发票增量',check:false},
					{title:'资金过桥',check:false},
					{title:'尽业调查',check:false},
					{title:'疑难核名',check:false},
					{title:'法律援助',check:false},
					{title:'工商疑难处理',check:false},
					{title:'税务疑难处理',check:false},
				]
			}
		},
		
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			drawerShow(){
				const self = this;
				self.is_show = !self.is_show
			},
			checkbox(i){
				const self = this;
				self.serviceClass[i].check = !self.serviceClass[i].check
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
	@import "../../assets/style/tingLis.css";
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	
	.selt-L{width: 22%;box-sizing: border-box;}
	.selt-R{width: 78%;}
	.selt-R .adrs{width: 160rpx;height: 44rpx;line-height: 44rpx;border: 1px solid #eee;box-sizing: border-box;padding: 0 10rpx;margin-right: 30rpx;}
	.selt-R .adrs:last-child{margin-right: 0;}
	.selt-R .adrs .text{width: 80%;text-align: center;font-size: 24rpx;}
	.selt-R .adrs .arrIcon{width: 18rpx;height: 12rpx;display: block;}
	
	.drawerBox{width: 85%;position: fixed; top: 88rpx;bottom: 0;right: 0;z-index: 50;background: #fff;padding: 30rpx 4%;box-sizing: border-box;transform: translateX(100%);transition: all .3s ease-out}
	.drawerBox.move{transform: translateX(0);}
	.drawerBox .items{flex-wrap: wrap;}
	.drawerBox .items .btn{width: 172rpx;line-height: 50rpx;height:50rpx;border-radius: 8rpx;background: #eee;margin: 0 30rpx 30rpx 0;}
	.drawerBox .items .btn.on{background: #0FA2E5;color: #fff;}
	.drawerBox .items .btn:nth-of-type(3n){margin-right: 0;}
</style>
