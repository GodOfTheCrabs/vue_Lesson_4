<!-- 8.Реалізуйте компонент, що виводить список об'єктів, де кожен об'єкт має вкладений список. 
     Використовуйте вкладені v-for для виведення елементів вкладеного списку. -->

<template>
    <div style="width: 350px; margin: 25px auto;" class="task-border">
        <p class="h4"> Task 8</p>
        <p class="h4">List of things to buy</p>
        <ul class="list-group">
            <li class="list-group-item list-group-item-primary" v-for="(item, index) in goShopping" :key="index">
                {{ item.name }}
                <ul class="list-group">
                    <li class="list-group-item list-group-item-secondary" v-for="(subItem, index) in item.subItems" :key="index">
                    {{ subItem }}
                    </li>
                </ul>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Task8',
        data() {
            return {
                goShopping: [
                    {
                    name: 'Products',
                    subItems: ['Bread', 'Milk', 'Eggs'],
                    },
                    {
                    name: 'Clothes',
                    subItems: ['Jacket', 'Shirt'],
                    },
                    {
                    name: 'Others',
                    subItems: ['Cleaning Supplies', 'Pens', 'Headphones'],
                    },
                ],
            }
        }
    }
</script>

<style>

</style>