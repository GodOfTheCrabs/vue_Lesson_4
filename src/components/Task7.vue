<!-- 7.За допомогою v-for, створіть таблицю, де кількість рядків і стовпців задається динамічно через інпут або інший елемент керування. -->

<template>
    <div class="task-border">
        <p class="h4">Task 7</p>
        <p class="h5 text-center">Create table</p>
        <div class="form-group">
            <label class="h5">Rows</label>
            <input type="number" class="form-control" style="width: 100px;" placeholder="Enter rows" v-model="table.rows" min="1" max="10">
        </div>
        <div class="form-group">
            <label class="h5">Columns</label>
            <input type="number" class="form-control" style="width: 100px;"  placeholder="Enter columns" v-model="table.columns" min="1" max="10">
        </div>
        <button class="btn btn-primary" @click="createTable">Create Table</button>
        <div v-if="isCreatedTable" :style="gridStyle">
            <div v-for="(item, index) in table.rows * table.columns" :key="index" class="grid-item">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Task7',
        data() {
            return {
                table: {
                    rows: 0,
                    columns: 0
                },
                isCreatedTable: false
            }
        },
        computed: {
            gridStyle() {
                return {
                    display: 'grid',
                    gridTemplateRows: `repeat(${this.table.rows}, 150px)`,
                    gridTemplateColumns: `repeat(${this.table.columns}, 150px)`,
                    gap: '10px',
                }
            },

            gridTable() {
                return Array.from({ length: this.table.rows * this.table.columns})
            }
        },
        methods: {
            createTable() {
                this.isCreatedTable = true
            }
        }
    }
</script>

<style scoped>
    .grid-item {
    background-color: lightblue;
    /* padding: 20px; */
    text-align: center;
    border: 1px solid #ccc;
    font-size: 14px;
    }
    .form-group {
        margin-top: 15px;
    }
    .btn {
        margin-top: 15px;
    }
    /* .grid-table {
        display: grid;
        grid-template-rows: repeat(3, 50px);
        grid-template-columns: repeat(3, 50px);
        gap: 10px;
    } */
</style>