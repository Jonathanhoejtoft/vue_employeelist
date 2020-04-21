<template>
    <div>
        <v-container>
            <v-row>
                <p>{{employee.employee_name}}</p>
            </v-row>
            <v-row>
                <p>{{employee.employee_age}}</p>
            </v-row>
            <v-row>
                <p>{{employee.employee_salary}}</p>
            </v-row>
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

</style>