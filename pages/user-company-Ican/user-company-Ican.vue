<template>
	<view>
		<view class="mglr4">
			<view class="pdtb15 ftw">代办服务</view>
			
			<view class="editLine fs13">
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>图片：</view>
					<view class="rr flex">
						<view class="upImg">
							<image src="../../static/images/service-img.png" mode=""></image>
						</view>
						<view class="fs11 color9">推荐尺寸：150px*150px</view>
					</view>
				</view>
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>企业名称：</view>
					<view class="rr flex">
						<input type="text" value="陕西纯粹云科技有限公司" placeholder="请输入企业的名称" placeholder-class="placeholder" />
					</view>
				</view>
				
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>营业执照：</view>
					<view class="rr flex">
						<view class="upImg">
							<image src="../../static/images/service-img.png" mode=""></image>
						</view>
					</view>
				</view>
				
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>标题：</view>
					<view class="rr flex">
						<input type="text" value="标题标题标题标题标题标题" placeholder="标题不得超出20字" placeholder-class="placeholder" />
					</view>
				</view>
				
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>服务区域：</view>
					<view class="rr selt-R flex">
						<view class="adrs flexRowBetween">
							<text class="text">陕西</text>
							<image class="arrIcon" src="../../static/images/add-icon2.png" mode=""></image>
						</view>
						<view class="adrs flexRowBetween">
							<text class="text">西安</text>
							<image class="arrIcon" src="../../static/images/add-icon2.png" mode=""></image>
						</view>
						<view class="adrs flexRowBetween">
							<text class="text">雁塔</text>
							<image class="arrIcon" src="../../static/images/add-icon2.png" mode=""></image>
						</view>
					</view>
				</view>
				
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>我能办：</view>
					<view class="rr flex canDoList">
						<view class="lis flex" v-for="(item,index) in canDoDate" :key="index" @click="canDoChange(index)">
							<image class="setIcon" :src="item.check==true?'../../static/images/add-icon1.png':'../../static/images/add-icon.png'" mode=""></image>
							<view class="tit">{{item.title}}</view>
						</view>
					</view>
				</view>
				
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>服务介绍：</view>
					<view class="rr selt-R flex">
						<textarea value="内容内容内容内容内容内容内容内容内容内容内容内容内容内容" placeholder="" />
					</view>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="mglr4">
			<view class="pdtb15 ftw">联系方式</view>
			
			<view class="editLine fs13">
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>联系电话：</view>
					<view class="rr flex">
						<input type="text" value="15986532356" placeholder="" placeholder-class="placeholder" />
					</view>
				</view>
				<view class="item flexRowBetween">
					<view class="ll flexRowBetween"><text class="red">*</text>联系人：</view>
					<view class="rr flex">
						<input type="text" value="尚明" placeholder="" placeholder-class="placeholder" />
					</view>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="submitbtn pdb25" style="margin-top: 80rpx;">
			<button class="btn" type="button" @click="Router.navigateTo({route:{path:'/pages/serviceDaTingDetailTwo/serviceDaTingDetailTwo'}})">确定</button>
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
				curr:0,
				check:false,
				canDoDate:[
					{check:true,title:'股票变更'},
					{check:false,title:'公司买卖'},
					{check:true,title:'代理记账'},
					{check:false,title:'资质代办'},
					{check:true,title:'商标过户'},
					{check:false,title:'专利过户'},
					{check:false,title:'挂靠地址'},
					{check:false,title:'执照加快'},
					{check:true,title:'代领发票'},
					{check:false,title:'发票增量'},
					{check:false,title:'资金过桥'},
					{check:false,title:'尽业调查'},
					{check:true,title:'疑难核名'},
					{check:false,title:'法律援助'},
					{check:false,title:'工商疑难处理'},
					{check:false,title:'税务疑难处理'}
				]
			}
		},
		
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			canDoChange(i){
				const self = this;
				self.canDoDate[i].check = !self.canDoDate[i].check
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
	@import "../../assets/style/editInfor.css";
	@import "../../assets/style/canDo.css";	
	
</style>
