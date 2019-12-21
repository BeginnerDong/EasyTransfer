<template>
	<view>
		
		<view class="mglr4">
			<view class="editLine whiteBj radius10 boxShaow mgt15">
				<view class="item flexRowBetween fs13">
					<view class="ll">企业名称：</view>
					<view class="rr">陕西纯粹云信息科技有限公司</view>
				</view>
				<view class="item flexRowBetween">
					<view class="ll">联系方式：</view>
					<view class="rr">15623568956</view>
				</view>
				<view class="item flexRowBetween">
					<view class="ll">企业地址：</view>
					<view class="rr">陕西省西安市雁塔区高新大都荟A座</view>
				</view>
			</view>
		</view>	
		
		<view class="submitbtn" style="margin-top: 260rpx;">
			<button class="btn" type="button" @click="Router.navigateTo({route:{path:'/pages/user-company-Ican/user-company-Ican'}})">编辑</button>
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
				num:false
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
	@import "../../assets/style/editInfor.css";
	
	.editLine .item{padding: 30rpx 4%;}
	.editLine .item .ll{color: #666;}
	.editLine .item .rr{font-size: 26rpx;}
</style>
