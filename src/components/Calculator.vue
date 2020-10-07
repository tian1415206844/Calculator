<style scoped>
	#template {}
</style>
<template>
	<div id="template">
		<table width="15%" border="1" align="center">
			<tr width='auto'>
				<th align='center' colspan='5'>简易计算器</th>
			</tr>
			<tr width='auto'>
				<th align='center' colspan='5' height="21">{{result}}</th>
			</tr>
			<tr>
				<td width="250"><input type="button" v-on:click="number" value="7" /></td>
				<td width="250"><input type="button" v-on:click="number" value="8" /></td>
				<td width="250"><input type="button" v-on:click="number" value="9" /></td>
				<td width="250"></td>
				<td width="250"></td>
			</tr>
			<tr>
				<td width="250"><input type="button" v-on:click="number" value="4" /></td>
				<td width="250"><input type="button" v-on:click="number" value="5" /></td>
				<td width="250"><input type="button" v-on:click="number" value="6" /></td>
				<td width="250"><input type="button" v-on:click="multiplicate" value="*" /></td>
				<td width="250"><input type="button" v-on:click="divide" value="/" /></td>
			</tr>
			<tr>
				<td width="250"><input type="button" v-on:click="number" value="1" /></td>
				<td width="250"><input type="button" v-on:click="number" value="2" /></td>
				<td width="250"><input type="button" v-on:click="number" value="3" /></td>
				<td width="250" rowspan='2'><input type="button" v-on:click="add" value="+" /></td>
				<td width="250"><input type="button" v-on:click="substract" value="-" /></td>
			</tr>
			<tr>
				<td width="250"><input type="button" v-on:click="number" value="0" /></td>
				<td width="250"><input type="button" v-on:click="number" value="." /></td>
				<td width="250"></td>
				<td width="250"><input type="button" v-on:click="equal" value="=" /></td>
			</tr>
		</table>
	</div>
</template>
<script>
	export default {
		data() {
			return {
				data1: '',
				data2: '',
				data: '',
				result: '',
				operator:''
			}
		},
		name: 'Calculator',
		methods: {
			add: function() {
				this.operator='';
				this.data1 = this.data;
				this.data = '';
				this.operator='+';
			},
			substract: function() {
				this.operator='';
				this.data1 = this.data;
				this.data = '';
				this.operator='-';
			},
			multiplicate: function() {
				this.operator='';
				this.data1 = this.data;
				this.data = '';
				this.operator='*';
			},
			divide: function() {
				this.operator='';
				this.data1 = this.data;
				this.data = '';
				this.operator='/';
			},
			equal: function() {
				this.result = '';
				this.data2 = this.data;
				this.data = '';
				if (this.data1 != '' && this.data2 != '') {
					switch (this.operator) {
						case '+':
							this.result = (parseFloat(this.data1) + parseFloat(this.data2)).toString();
						break;
						case '-':
							this.result = (parseFloat(this.data1) - parseFloat(this.data2)).toString();
						break;
						case '*':
							this.result = (parseFloat(this.data1) * parseFloat(this.data2)).toString();
						break;
						case '/':
							this.result = (parseFloat(this.data1) / parseFloat(this.data2)).toString();
						break;
						default:
							this.result = '';
					}
				}
			},
			number: function(event) {
				switch (event.target.value) {
				case '1':
					this.data += '1';
				break;
				case '2':
					this.data += '2';
				break;
				case '3':
					this.data += '3';
				break;
				case '4':
					this.data += '4';
				break;
				case '5':
					this.data += '5';
				break;
				case '6':
					this.data += '6';
				break;
				case '7':
					this.data += '7';
				break;
				case '8':
					this.data += '8';
				break;
				case '9':
					this.data += '9';
				break;
				case '.':
					this.data += '.';
				break;
				default:
				this.data += '';
			}
		}
	},
	mounted() {}
	}
</script>
