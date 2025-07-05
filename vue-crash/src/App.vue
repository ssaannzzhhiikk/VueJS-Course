<script>
export default {
  data () {
    return {
      name: "John Doe",
      status: 'pending',
      tasks: ['Task One', 'task Two', 'Task Three'],
      link: "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending';
      } else if ( this.status === 'pending') {
        this.status = 'inactive'
      } else {
        this.status = 'active';
      }
    }
  }
} 
</script>

<template>
  <h1> {{ name }} </h1>
  <p v-if="status === 'active'"> User is Active</p>
  <p v-else-if="status === 'pending'"> User is Pending</p>
  <p v-else>User is Inactive</p>

  <h2>Tasks:</h2>
  <ul>
    <li v-for="task in tasks" :key='task'> {{ task }} </li>
  </ul>
  <a v-bind:href="link" target="_blank"> Click </a>
  <br/>

<!--   <button v-on:click="toggleStatus"> Change Status </button> --> 
  <button @click="toggleStatus"> Change Status </button>

</template>

<style scoped>
  h1 {
    color: RED;
  }
</style>