<template>
	<view class="container">
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="swipperKun">
			<swiper-item>
				<view class="swiper-item">
					<image src="/static/kk1.jpg">
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="/static/kk2.jpg">
				</view>
			</swiper-item>
		</swiper>
		<view class="btnContainer" @click="handleClick">
			<button class="btn first" data-id="ji">
				鸡
			</button>
			<button class="btn first" data-id="ni">
				你
			</button>
			<button class="btn first" data-id="tai">
				太
			</button>
			<button class="btn first" data-id="mei">
				美
			</button>
			<button class="btn1 first" data-id="ngm">
				你干嘛哎哟
			</button>
			<button class="btn1 first" data-id="mgn">
				哟哎嘛干你
			</button>
			<button class="btn1 second" data-id="ring1">
				手鸡铃声
			</button>
			<button class="btn1 second" data-id="ring2">
				手鸡铃声
			</button>
			<button class="btn1 second" data-id="ring3">
				手鸡铃声
			</button>
			<button class="btn1 second" data-id="ring4">
				手鸡铃声
			</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				innerAudioContext: {}
			}
		},
		methods: {
			handleClick(e) {
				let type = e.target.dataset.id;
				this.innerAudioContext.stop();
				switch (type) {
					case 'ji':
						this.innerAudioContext.src = '/static/鸡.mp3';
						break;
					case 'ni':
						this.innerAudioContext.src = '/static/你.mp3'
						break;
					case 'tai':
						this.innerAudioContext.src = '/static/太.mp3';
						break;
					case 'mei':
						this.innerAudioContext.src = '/static/美.mp3'
						break;
					case 'ngm':
						this.innerAudioContext.src = '/static/你干嘛.mp3';
						break;
					case 'mgn':
						this.innerAudioContext.src = '/static/嘛干你.mp3'
						break;
					case 'ring1':
						this.innerAudioContext.src = '/static/铃声1.mp3';
						break;
					case 'ring2':
						this.innerAudioContext.src = '/static/铃声2.mp3'
						break;
					case 'ring3':
						this.innerAudioContext.src = '/static/铃声3.mp3';
						break;
					case 'ring4':
						this.innerAudioContext.src = '/static/铃声4.mp3'
						break;
					default:
						break;
				}
				type && this.innerAudioContext.play();

			}
		},
		onLoad() {
			this.innerAudioContext = uni.createInnerAudioContext();
		}
	}
</script>

<style lang="less">
	.swipperKun {
		margin-bottom: 20rpx;
	}

	// image {
	// 	// width: 95vw;
	// 	// height: 400upx;	
	// }
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}

	.btnContainer {
		display: flex;
		flex-wrap: wrap;
	}

	button {
		margin: 10upx;
	}

	.btn {
		flex: auto;
		width: 100upx;
		height: 100upx;

		// white-space: nowrap;
	}

	.btn1 {
		flex: auto;
	}
	.second {
		font-size: 32upx;
	}
</style>
