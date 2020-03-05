<template>
  <ul id="app">
    <li v-for="(user) in users" :key="user.id">
      {{ user.name }}:{{ user.id }}
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return {
      users: []
    }
  },
  mounted(){
    axios.get('/api/users').then(response=>{
      this.users = response.data;
    })
  }
}
</script>

<style>

</style>
