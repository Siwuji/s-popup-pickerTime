<template>
	<view class="content">
		<view>当前日期时间格式为:{{dateParms}}</view>
		<input @focus="showPicker" placeholder="默认格式yyyy-MM-dd" :value="value" />
		<button @click="changeDateParms">修改日期格式</button>
		<button @click="changeDateParms1">修改个怪异的格式</button>
		<button @click="changeDateParms2">来个中文?</button>
		
		<view class="default">
			注释:1.type默认为yyyy-MM-dd，可不传。2.能通过uni编译的小程序应该都可以使用,因我只试了微信和钉钉，所以其它小程序需要自行测试。
			
		</view>
		<sDatePicker ref="datePicker" @confirm="saveDate" :showClearBtn="true" :type="dateParms" ></sDatePicker>
	</view>
</template>

<script>
	import sDatePicker from '@/components/s-popup-picker/s-popup-picker.vue';
	export default {
		data() {
			return {
				dateParms: 'yyyy-MM-dd',
				value:""
			}
		},
		onLoad() {

		},
		components:{
			sDatePicker
		},
		methods: {
			showPicker(){
				this.$refs.datePicker.show();
			},
			saveDate(e) {
				//日期选择器【确认】事件
				console.log(e)
				this.value = e;
			},
			changeDateParms(){
				this.dateParms = "yyyy-MM-dd HH:mm:ss"
			},
			changeDateParms1(){
				this.dateParms = "yyyy HH:mm"
			},
			changeDateParms2(){
				this.dateParms = "yyyy HH时"
			}
		}
	}
</script>

<style>
	.content{
		padding: 24rpx;
	}
	
	.content > input{
		display: block;
		margin: 24rpx 0;
		padding: 12rpx 8rpx;
		border: 1px solid #EEEEEE;
		font-size: 26rpx;
	}
	.content > button{
		margin-bottom: 24rpx;
	}
	
	.default{
		color: #666666;
		font-size: 24rpx;
	}
</style>
