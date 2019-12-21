<template>
	<view>
		<view><image style="width: 100%;height: 493rpx;display: block;" src="../../static/images/login-icon.png" mode="widthFix"></image></view>
		
		<view>
			<view class="orderNav pdlr4 borderB1 flexRowBetween fs15">
				<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">普通用户登录</view>
				<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">经纪人登录</view>
			</view>
			<view class="loginEdit" v-show="curr==1">
				<view class="item flex">
					<view class="ll">账号</view>
					<view class="rr">
						<input type="text" value="" placeholder="手机号/邮箱/用户名" placeholder-class="placeholder" />
					</view>
				</view>
				<view class="item flex">
					<view class="ll">密码</view>
					<view class="rr">
						<input type="text" value="" placeholder="请输入6~20位密码" placeholder-class="placeholder" />
					</view>
				</view>
				<view class="flex pdt5">
					<view class="pubColor fs13 mgl10" @click="Router.navigateTo({route:{path:'/pages/register/register'}})">立即注册</view>
				</view>
			</view>
			
			<view class="loginEdit" v-show="curr==2">
				<view class="item flex">
					<view class="ll">账号</view>
					<view class="rr">
						<input type="text" value="" placeholder="经纪人手机号/邮箱/用户名" placeholder-class="placeholder" />
					</view>
				</view>
				<view class="item flex">
					<view class="ll">密码</view>
					<view class="rr">
						<input type="text" value="" placeholder="请输入6~20位密码" placeholder-class="placeholder" />
					</view>
				</view>
				<view class="flex pdt5">
					<view class="pubColor fs13 mgl10" @click="Router.navigateTo({route:{path:'/pages/register/register'}})">立即注册</view>
				</view>
			</view>
			
			<view class="submitbtn" style="margin-top: 120rpx;">
				<button class="btn" type="button" @click="Router.navigateTo({route:{path:'/pages/company-wantSell/company-wantSell'}})">登录</button>
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
				curr:1
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeCurr(curr){
				const self = this;
				if(curr!=self.curr){
					self.curr = curr
				}
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
@import "../../assets/style/orderNav.css";	
.orderNav .tt{width: 50%;}
.orderNav .tt.on::after{ width: 200rpx;}

.loginEdit{padding: 0 10%;}
.loginEdit .item{padding:40rpx 20rpx 0 20rpx;border-bottom: 1px solid #eee;line-height: 60rpx;box-sizing: border-box;}
.loginEdit .item .ll{width: 20%;font-size: 30rpx;}
.loginEdit .item .icon{width: 44rpx; height: 44rpx;}
.loginEdit .item .rr{width: 80%;font-size: 26rpx;}
.loginEdit .item .rr input{width: 100%;height: 60rpx; display: block;font-size: 24rpx;}
.loginEdit .item .rr .placeholder{font-size: 26rpx;}
</style>

