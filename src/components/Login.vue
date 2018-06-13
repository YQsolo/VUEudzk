<template>
	<div id="login">
		<div id="login_center">
			<div>
				<h1>LNG智能控制</h1>
			</div>
			<div id="username">
				<el-input placeholder="请输入用户名" suffix-icon="el-icon-service" name="username" v-model="username" class="logininput"></el-input>
			</div>
			<div id="password">
				<el-input placeholder="请输入密码" suffix-icon="el-icon-search" name="password" v-model="password" type="password" class="logininput"></el-input>
	  	</div>
	  	<div>
				<el-button type="primary" id="loginbutton" @click='login'>Login</el-button>  	
			</div>
		</div>
	</div>
</template>
<script>
  export default{
  	name:'login',
 	  data(){
 		  return{
 		  	username:'',
 		  	password:''
 			}
 		},
 		methods:{
 			login(){
		    this.$ajax({
		     method: 'get',
		     url: '/userinfo/login',
		     params: {
				   userName: this.username,
				   password: this.password
				  }
		    }).then( (res) =>{
		     console.log(res);
		     if(res.data.status == 'error'){
		     	alert('用户名或密码错误,请重新输入...');
		     }
		     else{
		     	this.$router.push('/main');
		     }
		    })
	 		}
 		},
 		mounted(){
 

 		}
 }
</script>
<style lang="scss" scoped>
$background:'../assets/demo-1-bg.jpg';
#login{
	overflow:hidden;
	width:100%;
	height:100%;
	background:url($background);
}
#login_center{
	position:absolute;
	width:30%;
	height:35%;
	left:0;
	top:0;
	right:0;
	bottom:0;
	margin:auto;
	.logininput{
		width:80%;
		margin:0 auto;
	}
	h1{
		color:#fff;
		font-size:36px;
	}
	div{
		display:block;
		height:32px;
		line-height: 32px;
		margin-top:20px;
	}
	#loginbutton{
		width:80%;
		font-size:16px;
		font-weight:bold;
	}
}
</style>