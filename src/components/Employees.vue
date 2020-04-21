<template>
<div>
    <div v-for="employee in employees" v-bind:key="employee.id">      
        <EmployeeItem v-bind:employee="employee" />
    </div>
</div>
</template>

<script>
import EmployeeItem from './EmployeeItem.vue';
export default {
    name: "Employees",
    components:{
    EmployeeItem
    },
    props:['employees']
}
</script>
<style scoped>

</style>
