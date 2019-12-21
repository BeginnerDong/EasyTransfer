<template>
	<view>
		<view class="screenList fs12 pdt15">
			<view class="item flexRowBetween">
				<view class="ll">公司类别：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in category" :key="index" :class="currCategory == index?'on':''" @click="seltCategory(index)">{{item}}</view>
				</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">省份：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in province" :key="index" :class="currProvince == index?'on':''" @click="seltProvince(index)">{{item}}</view>
				</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">热门标签：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in hotLable" :key="index" :class="currHotLable == index?'on':''" @click="seltHotLable(index)">{{item}}</view>
				</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">热门公司：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in hotCompany" :key="index" :class="currHotCompany == index?'on':''" @click="seltHotCompany(index)">{{item}}</view>
				</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">注册年限：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in registerReg" :key="index" :class="currRegisterReg == index?'on':''" @click="seltRegisterReg(index)">{{item}}</view>
				</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">注册资本：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in registerCapital" :key="index" :class="currRegisterCapital == index?'on':''" @click="seltRegisterCapital(index)">{{item}}</view>
				</view>
			</view>
			<view class="item flexRowBetween">
				<view class="ll">纳税性质：</view>
				<view class="rr flex">
					<view class="btn" v-for="(item,index) in payTaxes" :key="index" :class="currPayTaxes == index?'on':''" @click="seltPayTaxes(index)">{{item}}</view>
				</view>
			</view>
		</view>
		
		<view class="submitbtn" style="margin-top: 100rpx;">
			<button class="btn" type="button">确定</button>
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
				currCategory:0,
				category:['不限','空壳公司','实体公司'],
				currProvince:0,
				province:['不限','北京','天津','河北','陕西','山西','内蒙古','辽宁','吉林','上海','江苏','内蒙古','浙江','安徽','福建','四川','湖南','湖北','河南'],
				currHotLable:0,
				hotLable:['不限','免费转','买过社保','银行流水大','政府/国企背景','外资背景','国家局名称'],
				currHotCompany:0,
				hotCompany:['不限','资质类公司','商标类公司','网络资产','专利/制作权','车牌类公司','金融/投资','香港公司'],
				currRegisterReg:0,
				registerReg:['不限','1年以下','1年及以上','2年及以上','3年及以上','5年及以上','10年及以上'],
				currRegisterCapital:0,
				registerCapital:['不限','10万以下','10万及以上','50万及以上','100万及以上','1000万及以上'],
				currPayTaxes:0,
				payTaxes:['不限','小规模','一般纳税人']
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			
			seltCategory(index){
				const self = this;
				self.currCategory = index
			},
			seltProvince(index){
				const self = this;
				self.currProvince = index
			},
			seltHotLable(index){
				const self = this;
				self.currHotLable = index
			},
			seltHotCompany(index){
				const self = this;
				self.currHotCompany = index
			},
			seltRegisterReg(index){
				const self = this;
				self.currRegisterReg = index
			},
			seltRegisterCapital(index){
				const self = this;
				self.currRegisterCapital = index
			},
			seltPayTaxes(index){
				const self = this;
				self.currPayTaxes = index
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
	@import "../../assets/style/xieyiAlert.css";
	page{padding-bottom: 60rpx;}
	.screenList .item{align-items: flex-start;margin-bottom: 10rpx;}
	.screenList .ll{width: 22%;color: #999;text-align: right;padding-right: 20rpx;box-sizing: border-box;}
	.screenList .rr{width: 78%; flex-wrap: wrap;}
	.screenList .rr .btn{padding: 0 16rpx;line-height: 40rpx;border-radius: 8rpx;background: #eee;margin:0 30rpx 30rpx 0;}
	.screenList .rr .btn.on{background: #0FA2E5; color: #fff;}
</style>
