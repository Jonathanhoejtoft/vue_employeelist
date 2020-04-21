<template>
    <div>
        <v-container>
                <div class="employee-card">
            <v-row>
                <v-col cols="3">
                    <div class="right-section">
                        <div v-if='employee.profile_image === "" '>
                        <v-img src="../assets/avatar.png"></v-img>
                        </div>
                        <div v-else>
                            <v-img v-bind:src="employee.profile_image"></v-img>
                        </div>
                    </div>
                </v-col>
                <v-col cols="6">
                    <v-row>
                        <h3>{{employee.employee_name}}</h3>
                    </v-row>
                    <v-row>
                        <div class="empAge">
                            <p>Age: </p>
                            <p>{{employee.employee_age}}</p>
                        </div>
                    </v-row>
                    <v-row>
                        <div class="empSalary">                       
                            <p>Salary: </p>                       
                            <p>{{employee.employee_salary}}</p>
                       
                        </div>
                    </v-row>
                </v-col>
            </v-row>
                </div>             
        </v-container>

    </div>
</template>
<script>
export default {
    name:"Employeeitem",
    components:{},
    props:['employee']
}
</script>
<style scoped>
.right-section{
    background: red;
}
.employee-card{
    width:60%;
    margin: auto;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
.empAge p,.empSalary p{
    display: inline;
}
</style>