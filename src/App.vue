<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <p>服了啊！</p>
     <ul >
       <li v-for="(item) in users" :key="item.id">
           {{item.id}}-{{item.name}}
       </li>
     </ul>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  name: 'App',
  data(){
    return {
      users:[]
    }
  },
  mounted() {
    const api="/api/users"
    axios.get(api).then(res=>{
      console.log(res)
      this.users=res.data
    })
  },
 
}
</script>


