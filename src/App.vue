<template>
  <UserCard v-bind:UsName="UsName" v-bind:FullName="FullName"/>
  <button v-on:click="getList()">get data</button>
</template>

<script>
import UserCard from './components/UserCard.vue'

export default {
  name: 'App',
  components: {
    UserCard
  },
  methods : {
    getList(){
      this.axios.get('https://randomuser.me/api').then((response) => {console.log(response.data)})
    },
    data(){
      return {
        UsName: 'gull',
        FullName: 'Серый Олежиков'
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
