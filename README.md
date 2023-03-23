# s-popup-pickerTime

日期选择组件

## 基本用法
	将s-popup-picker文件夹复制到components文件夹中,import+components引入。

    <template>
    	<view class="content">
    		<view>当前日期时间格式为:{{dateParms}}</view>
    		<input @focus="showPicker" placeholder="默认格式yyyy-MM-dd" :value="value" />
    		<sDatePicker ref="datePicker" @confirm="saveDate" :defaultValue="value" :showClearBtn="true" :type="dateParms" :YearInterval="YearInterval"></sDatePicker>
    	</view>
    </template>
    
    <script>
    	import sDatePicker from '@/components/s-popup-picker/s-popup-picker.vue';
    	export default {
    		data() {
    			return {
    				dateParms: 'yyyy-MM-dd',
    				value:"",
					YearInterval:[10,1]
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
    			}
    		}
    	}
    </script>


### Events
| 参数      | 说明     | 是否必传    |
| -------- | ------ | ------ |
| defaultValue | 默认值 | 否 |
| showClearBtn | 显示清空按钮 | 否 |
| type | 时间格式 | 否 |
| YearInterval | 年份区间 | 否 |

| 事件名      | 说明     | 返回值    |
| -------- | ------ | ------ |
| @confirm | 选中日期事件 | string |

