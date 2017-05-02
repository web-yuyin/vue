<template>
	<div id="app">
		<div class="side">{{code}}</div>
 		<div v-html='styleCode'></div>
	</div>
</template>

<script>
export default {
	name: 'app',
	components: {

	},
	data (){
		return {
  			code : '',
  			finalCode : '.side { width:50%; background:#ccc; font-size:30px; color:red; border:1px solid #000; padding:10px; }'
  		}
	},
	created (){
		var n =0;
		setInterval(()=>{
			this.code = this.finalCode.substring(0, n);
			n ++;
		},50);
	},
	methods: {

  	},
	computed: {
		styleCode(){
			return '<style>'+ this.code +'</style>';
		}
	}
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
