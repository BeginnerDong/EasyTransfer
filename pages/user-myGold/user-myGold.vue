<template>
	<view>
		<view class="">
			<view class="myExtendTop white flexCenter center">
				<view class="">
					<view class="money">500<text class="fs14 mgl5">个</text></view>
					<view class="fs14">总金币</view>
				</view>
			</view>
			
			<view class="myRowBetween pdlr4">
				<view class="item flexRowBetween" v-for="(item,index) in goldDate" :key="index">
					<view class="ll">
						<view>分享</view>
						<view class="fs12 color6">2019-12-20</view>
					</view>
					<view class="rr red fs18">+50</view>
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
				goldDate:[{},{},{}]
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
	.myExtendTop{width: 100%;height: 320rpx; background: #0FA2E5;}
	.myExtendTop .money{font-size: 80rpx; line-height:88rpx;}
	
	.myRowBetween .item .rr{font-size: 30rpx;}
</style>
