<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="text-area">
			<text class="title">{{title}}</text>
			<button type="default" @click="send()">qqq</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
			}
		},
		onLoad() {
				console.log(1)
			uni.request({
			     url:'https://qcxlld.fn.thelarkcloud.com/toutiaohello',
			     success:res=>{
							  console.log(res.test)
							  this.title= res.data
			   },
			     fail:()=>{console.log(22)
			   },
			     complete:=>{
			   }
			})
		},
		methods: {
			send:function(){
				// var title
				uni.request({
				     url:'https://qcxlld.fn.thelarkcloud.com/toutiaohello',
				     success:res=>{
								  console.log(res.test)
								  // title= res.data
				   },
				     fail:()=>{console.log(22)
				   },
				     complete:=>{
						 
				   }
				})
				// this.title = title
			}
			
		}
	}
	// 在小程序中，需要先下载 SDK，并移动至 libs 目录
</script>

// <script>
// 	const InspireCloud = require ('@byteinspire/js-sdk');
// 	const serviceId = 'qcxlld'; // 替换成你的 serviceId，可在后台「设置」页面获取
	
// 	// 初始化
// 	const inspirecloud = new InspireCloud({ serviceId });
	
// 	// 函数名称
// 	const fnName = 'toutiaohello';
	
// 	// 通过 inspirecloud.run 调用云函数
// 	inspirecloud.run(fnName, { message: 'toutiaohello' })
// 	  .then(data => {
// 	  		return {
// 	  			title: message
// 	  		}
		  
// 	    // 处理正常结果
// 	  })
// 	  .catch(error => {
// 	    // 处理异常结果
// 	  });
// </script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
