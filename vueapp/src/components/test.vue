<template>
  <div class="test">
    <h1>{{ title }}</h1>
    <input type="text" v-model="title"><br />
    <p v-if="showName">{{ user.firstName }} {{user.lastName}} == {{ fullName }}</p>
    <ul>
      <li v-for="item in items">{{ item.title }}</li>
    </ul>
    <button v-on:click="greet">Say greeting</button>
  </div>
</template>

<script>
  export default {
    name: 'test',
    data() {
      return {
        title: 'Hello World',
        user: {
          firstName: 'John',
          lastName: 'Doe'
        },
        showName: true,
        items: [
          { title: 'Item one' },
          { title: 'Item two' }
        ]
      }
    },
    methods: {
      greet: function() {
        alert('Hello');
      }
    },
    computed: {
      fullName: function() {
        return this.user.firstName+' '+this.user.lastName;
      }
    }
  }
</script>

<style scoped>

</style>
