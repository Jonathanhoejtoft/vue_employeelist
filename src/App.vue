<template>
  <div id="app">
    <Header />
  <Employees v-bind:employees="employees" />
  </div>
</template>

<script>
import Employees from './components/Employees.vue';
import Header from './components/layout/header.vue'
import axios from 'axios';
export default {
  name: 'App',
  components: {
    Employees,
    Header
  },
  data(){
    return{
      employees:[]
    }
  },
created(){
  axios.get('http://dummy.restapiexample.com/api/v1/employees')
  .then(res => this.employees = res.data.data)
  .catch(err => console.log(err));
}
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  margin:0;
  padding: 0;
}
</style>
