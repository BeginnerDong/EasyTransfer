
<script>
	import token from "./common/token.js"
	export default {
		onLaunch: function() {	
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import "/assets/style/style.css";
	@import "/assets/style/quill.css";
	/* rgb(83, 125, 235) */
	
	uni-swiper .uni-swiper-dots-horizontal{line-height: 8px;bottom: 5px;}
	
	uni-tabbar .uni-tabbar__icon{width: 44rpx;height: 44rpx;}
	uni-page-head .uni-page-head__title{font-weight: normal;}
	uni-swiper .uni-swiper-dot{background: #eee;}
	
	.ql-editor img{
		max-width: 100%;
		margin: 0 auto;
	}
	
</style>
