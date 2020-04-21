<template>
    <div>
        <p>{{employee.employee_name}}</p>
        <span>{{employee.employee_age}}</span><br>
        <span>{{employee.employee_salary}}</span>

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