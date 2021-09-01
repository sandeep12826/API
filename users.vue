<template>
     <div>
	 <h1>StudentList</h1>
	 <div>
	     <table border="1px">
		     <tr>
			     <td>id</td>
				 <td>email</td>
				 <td>frist_name</td>
				 <td>last_name</td>
				 <td>avatar</td 
			 </tr>
			 <tr v-for="item in list" v-bind:key="item.id">
			     <td>{{id}}</td>
				 <td>{{email}}</td>
				 <td>{{frist_name}}</td>
				 <td>{{last_name}} </td>
				 <td>{{avatar}} </td> 
			 </tr>
		 </table?
	 </div>
	 </div>
</template>
<script>
import Vue from 'vue';
import VueAxios from 'vue-axios';
import axios from 'axios';
Vue.use(VueAxios,axios)
export default{
    name: "users",
	data()
	{
	   return{
	      list:undefined
		}
	},
	mounted()
	{
	Vue.axios.get('https://reqres.in/api/users?page=2')
	.then(resp=>{
	     this.list=resp.data.data
	     console.warn(resp.data.data)
		 })
	}
}
</script>