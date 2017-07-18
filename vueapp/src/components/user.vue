<template>
  <div class="users">
     <h1>Users</h1>
     <form v-on:submit="addUser">
       <input type="text" v-model="newUser.name" placeholder="Enter name">
       <input type="email" v-model="newUser.email" placeholder="Enter e-mail">
       <input type="submit" value="Add user">
     </form>
     <ul>
       <li v-for="user in users">
         {{ user.name }}: {{ user.email }}
       </li>
     </ul>
  </div>
</template>

<script>
  export default {
    name: 'users',
    data() {
      return {
        newUser: {},
        users: [
          { name: 'John Doe', contacted: true, email: 'test@example.com'},
          { name: 'Jane Doe', contacted: true, email: 'test@example.com'},
          { name: 'Amanda Fox', contacted: true, email: 'test@example.com'}
        ]
      }
    },
    methods: {
      addUser: function(e) {
        this.users.push(this.newUser);
        e.preventDefault();
      }
    }
  }
</script>

<style scoped>

</style>
