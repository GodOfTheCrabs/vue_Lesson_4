<!-- 4.творіть динамічний список елементів, де кожен елемент має випадковий колір фону та розмір шрифту, згенеровані методом при створенні компоненту. -->

<template>
    <div style="margin: 25px auto; width: 600px;" class="task-border">
        <p class="h4">Task 4</p>
        <ul class="list-group">
            <li class="list-group-item" 
            :class="[backgroundColor[getRandomBackgroundColor()], fontSize[getRandomFontSize()]]"  
            >
            This is a primary list group item
        </li>
            <li class="list-group-item" 
            :class="[backgroundColor[getRandomBackgroundColor()], fontSize[getRandomFontSize()]]"
            >This is a secondary list group item</li>
            <li class="list-group-item"
            :class="[backgroundColor[getRandomBackgroundColor()], fontSize[getRandomFontSize()]]"
            >This is a success list group item</li>
            <li class="list-group-item"
            :class="[backgroundColor[getRandomBackgroundColor()], fontSize[getRandomFontSize()]]"
            >This is a danger list group item</li>
            <li class="list-group-item"
            :class="[backgroundColor[getRandomBackgroundColor()], fontSize[getRandomFontSize()]]"
            >This is a warning list group item</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Task4',
        data() {
            return {
                backgroundColor: [
                'list-group-item-primary',
                'list-group-item-secondary',
                'list-group-item-success',
                'list-group-item-danger',
                'list-group-item-warning',
                ],
                fontSize: [
                    'h1',
                    'h2',
                    'h3',
                    'h4',
                    'h5',
                    'h6',
                ],
            }           
        },
        methods: {
            getRandomBackgroundColor() {
                return Math.floor(Math.random() * 6)
            },
            getRandomFontSize() {
                return Math.floor(Math.random() * 7)
            },
        }
    }
</script>

<style scoped>

</style>