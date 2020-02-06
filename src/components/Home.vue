<template>
  <div>
    <table class="table table-striped">
      <tr>
        <th>id</th>
        <th>name</th>
        <th>email</th>
        <th>address</th>
      </tr>

      <tr v-for="user in users" :key="user.id">
        <td>
          {{user.id}}
        </td>
        <td>
          {{user.name}}
        </td>
        <td>
          {{user.email}}
        </td>
        <td>
          {{user.address.city}}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
  import axios from 'axios';

export default {
  data() {
    return {
      users:''
    }
  },
  created(){
    //var mv = this.users
   axios.get('https://jsonplaceholder.typicode.com/users')
   .then(res => this.users = res.data)
     
   }
   
  
}
</script>