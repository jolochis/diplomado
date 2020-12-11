<template>

  <HelloWorld />
</template>

<script>

import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
input {
	width: 89.7%;
	height: 40px;  
	white-space: pre;
	word-break: break-word;
	border-radius: 5px;
}

label{
	display: inline-block;
	width: 180px;
}

select{
	width: 90%;
	height: 40px;
	border-radius: 5px;
}

h3{
	text-align: 80px;
	color: 	#0000CD;
	font-family: Arial;
	font-size: x-large;
}
form {
	padding-left: 80px;
}


.button {
	background-color: #00BFFF; 
	border: none;
	color: white;
	padding: 10px 27px;
	text-align: center;
	text-decoration: none;
	display: inline-block;
	font-size: 16px;
	border-radius: 10px;
}

table{
	border:1;
	width: 100%;
	border-collapse:separate
}


.F0{
	background-color: #4169E1; 
	color: white;
	padding: 10px 40px;
	text-decoration: none;  
}

.F1{
	background-color: #A9A9A9; 
	color: black;
	padding: 10px 40px;
	text-decoration: none;  
}

.F2{
	background-color: #DCDCDC; 
	color: black;
	padding: 10px 40px;
	text-decoration: none;  
}
</style>
