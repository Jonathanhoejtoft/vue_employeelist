<template>
    <div>
        <v-container>
           

                <div class="employee-card">
            <v-row>
                <v-col cols="3" >
                    <div class="right-section">
                        <div v-if='employee.profile_image === "" '>
                        <v-img style="border-radius:50%" src="../assets/avatar.png"></v-img>
                        </div>
                        <div v-else>
                            <v-img v-bind:src="employee.profile_image"></v-img>
                        </div>
                    </div>
                </v-col>
                <v-col cols="6" style="margin-left:15px">
                    <v-row class="empName" >
                        <h3>{{employee.employee_name}}</h3>
                    </v-row>
                    <v-divider class="empDivider"></v-divider>
                      <v-row style="margin-bottom:10px">
                        <div class="empAge c_chip">
                            <b>{{employee.employee_age}}</b>
                            <p> years </p>
                            <v-icon>mdi-cake-variant</v-icon>
                        </div>
                    </v-row>
                    <v-row>
                        <div class="empSalary c_chip">
                            <b>{{employee.employee_salary}}</b>
                            <p> income </p>                 
                            <v-icon>mdi-work</v-icon>      
                            <i class="fas fa-hand-holding-usd"></i>                       

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
    margin-left: 15px;
}
.employee-card{
    width:40%;
    margin: auto;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
.empAge p,.empSalary p{
    display: inline;
}
.empAge i, .empSalary i{
    font-size:20px;
}
.empName{
    margin-bottom: 15px ;
}
.empDivider{
    margin-bottom: 15px;
}

.c_chip{
    background: #6cc0f3;
    border-radius: 25px;
    padding: 10px;
}
</style>