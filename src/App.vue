<template>
  <div id="app">
    <Header />
    <button class="toggleBtn" @click="this.toggleView">Toggleview - {{this.viewType}}</button>
  <div v-if="tableView === false">
  <Employees v-bind:employees="employees" />
  </div>
  <div v-else>
    <v-container>
      <v-data-table
      :headers="headers"
      :items="employeesTable"
      :sort-by="['employee_salary', 'employee_age']"
      :sort-desc="[false, true]"
      multi-sort
      class="elevation-1"
    ></v-data-table>
    </v-container>
  </div>
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
      headers: [
          {
            text: 'Employees',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: 'employee_name', value: 'employee_name' },
          { text: 'employee_salary', value: 'employee_salary' },
          { text: 'employee_age', value: 'employee_age' },
          { text: 'profile_image', value: 'profile_image' },
        ],
        employeesTable: [],
      employees:[],
      tableView:true,
      viewType:''
    }
  },
  methods:{
    toggleView(){
      this.tableView = !this.tableView;
      this.viewType = this.tableView == true ? 'datatable' : 'customview';
      console.log(this.tableView);
    }
  },
created(){
  axios.get('http://dummy.restapiexample.com/api/v1/employees')
  .then(res => this.employees = res.data.data)
  .catch(err => console.log(err));
},
mounted(){
  this.viewType = this.tableView == true ? 'datatable' : 'customview';

  axios.get('http://dummy.restapiexample.com/api/v1/employees')
  .then(res => this.employeesTable = res.data.data)
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
.toggleBtn{
  background: #39841a;
    color: white;
    padding: 10px;
    margin-top: 10px;
}
.toggleBtn:hover{
  background: #55af30;
}
</style>
