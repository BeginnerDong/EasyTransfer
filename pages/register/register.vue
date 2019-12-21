<template>
	<view>
		<view><image style="width: 100%;height: 493rpx;display: block;" src="../../static/images/login-icon.png" mode="widthFix"></image></view>
		
		<view>
			<view class="loginEdit">
				<view class="item flex" style="padding-top: 0;">
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
				<view class="item flex">
					<view class="ll" style="width: 30%;">再次确认</view>
					<view class="rr" style="width: 70%;">
						<input type="text" value="" placeholder="请输入6~20位密码" placeholder-class="placeholder" />
					</view>
				</view>
			</view>
			
			<view class="submitbtn" style="margin-top: 120rpx;">
				<button class="btn" type="button" @click="Router.navigateTo({route:{path:'/pages/login/login'}})">注册</button>
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
				is_show:false
			}
		},
		
		onLoad(options) {
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

.loginEdit{padding: 0 10%;}
.loginEdit .item{padding:40rpx 20rpx 0 20rpx;border-bottom: 1px solid #eee;line-height: 60rpx;box-sizing: border-box;}
.loginEdit .item .ll{width: 20%;font-size: 30rpx;}
.loginEdit .item .icon{width: 44rpx; height: 44rpx;}
.loginEdit .item .rr{width: 80%;font-size: 26rpx;}
.loginEdit .item .rr input{width: 100%;height: 60rpx; display: block;font-size: 24rpx;}
.loginEdit .item .rr .placeholder{font-size: 26rpx;}
</style>

