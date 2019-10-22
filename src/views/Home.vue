<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div v-for="todo in todos">
    <HelloWorld v-bind:todo="todo" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios';
import HelloWorld from "../components/HelloWorld";

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data() {
    return {
      testdata: 'hello',
      todos : []
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    // eslint-disable-next-line no-console
            .then(res =>  this.todos = res.data).catch();
  }
}
</script>
