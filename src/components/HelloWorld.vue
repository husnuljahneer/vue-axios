<template>
  <div>
      <h2>Users</h2>
    <div v-for="users in users" :key="users.id"> 
      <p>Username : {{ users.name }} : {{ users.email }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      users: []
    }
  },
  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/users')
      .then(response => {
        this.users = response.data
      })
  }  
}
</script>
