<!-- 5.Реалізуйте динамічне змінення стилів елемента (наприклад, зміна позиції, коліру, розміру) за допомогою CSS Transitions або Animations при натисканні кнопки. -->
<template>
        <div class="task-border">
            <p class="h4">Task 5</p>
            <p class="h5"
            :class="[{red : isRed}, {underline: isUnderline}]"
            >This text can be change</p>
            <v-btn variant="outlined" @click="changeStyle">Change style</v-btn>
        </div>
</template>

<script>
    export default {
        name: 'Task4',
        data() {
            return {
                isRed: false,
                isUnderline: false
            }           
        },
        methods: {
            changeStyle() {
                this.isRed = !this.isRed
                this.isUnderline = !this.isUnderline
            }
        }
    }
</script>

<style scoped>

.red {
    color: red;
}

.underline {
    text-decoration: underline;
}

</style>