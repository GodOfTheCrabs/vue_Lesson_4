<!-- 10.Виведіть список елементів, використовуючи v-for, і додайте умову v-if для фільтрації елементів. -->

<template>
    <div style="width: 350px; margin: 25px auto;" class="task-border">
        <p class="h4">10.</p>
        <ul class="list-group">
            <template v-for="(employee, index) in employees">
                <li class="list-group-item list-group-item-info" v-if="employee.position === 'Developer'" :key="index">
                    Name: {{ employee.name }} <br> Age: {{ employee.age }} <br> Position: {{ employee.position }}
                </li>
            </template>
        </ul>
    </div>
</template>
    
<script>
    export default {
        name: 'Task10',
        data() {
            return {
                employees: [
                    { id: 1, name: 'John Doe', age: 30, position: 'Developer' },
                    { id: 2, name: 'Jane Smith', age: 25, position: 'Designer' },
                    { id: 3, name: 'Sam Johnson', age: 35, position: 'Manager' },
                    { id: 4, name: 'Will Betcher', age: 25, position: 'Developer' },
                    { id: 5, name: 'Steve Overbeck', age: 40, position: 'Manager' },
                ]
            }
        }
    }
</script>

<style>

</style>