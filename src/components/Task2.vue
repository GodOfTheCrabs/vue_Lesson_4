<!-- 2.Реалізуйте форму, де при submit ви використовуєте модіфікатор .prevent, 
    і дані форми обробляються методом Vue інстанса, який також валідує їх на правильність введення перед відправкою. -->

<template>
    <div class="task-border">
        <p class="h4">Task 2</p>
        <form class="form-task" @submit.prevent="handleSubmit">
            <p class="h5 text-center">Form for registration</p>
            <div class="form-group">
                <label class="h5">Login</label>
                <input type="text" class="form-control" placeholder="Enter Login" v-model="formData.name">
                <span v-if="errors.name" class="text-danger">{{ errors.name}}</span>
            </div>
            <div class="form-group">
                <label class="h5">Password</label>
                <input type="password" class="form-control" placeholder="Password" v-model="formData.password">
                <span v-if="errors.password" class="text-danger">{{ errors.password}}</span>
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
        </form>
        
    </div>
</template>

<script>
    export default {
        name: 'Task2',
        data() {
            return {
                formData: {
                    name: '',
                    password: ''
                },
                errors: {},
                submittedData: null
            }
        },
        methods: {
            validateForm() {    
                const errors = {}

                if(!this.formData.name) {
                    errors.name = 'Login is empty'
                }

                if(!this.formData.password) {
                    errors.password = 'Password is empty'
                } else if (this.formData.password > 8) {
                    errors.password = 'Password must be 8 characters long'
                }

                this.errors = errors

                return Object.keys(errors).length === 0
            },
            handleSubmit() {
                if(this.validateForm()) {
                    this.submittedData = this.formData
                    alert('Form submitted successfully')

                    this.formData.name = ''
                    this.formData.password = ''
                    this.errors = {}
                } else {
                    alert('Correct errors in the form')
                }
            }
        }
    }
</script>

<style scoped> 
    .form-task {
        width: 350px;
        margin: 0 auto;
        text-align: left;
    }
    .form-group {
        margin-top: 25px;
    }
    .btn {
        margin-top: 25px;
    }
    label {
        margin-bottom: 10px;
    }
    .form-control {
        border: 1px solid black;
    }
</style>