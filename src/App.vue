<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
     <ul >
       <li v-for="item in users" :key="item.id">
           {{item.name}}

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
    const api="http://localhost:3001/api/users"
    axios.get(api).then(res=>{
      this.users=res.data
    })
  },
 
}
</script>


