<!-- 1.Створіть компонент, де кожен клік на кнопку зберігає поточний час кліка в масив і виводить цей масив на екран. -->
<!-- 3.Створіть два методи і динамічно змінюйте обробник події кліка між цими методами на основі деякої умови (наприклад, значення змінної). -->

<template>
    <v-col class="task-border">
        <p class="h4">Task 1, 3</p>
        <v-row>
            <v-col>
                Time:
            </v-col>
            <v-col>
                <v-btn variant="outlined" v-on:[modifier]="catchTime">Catch Time</v-btn>
            </v-col>
            <v-col>
                <v-btn variant="outlined" @click="changeModifier">Change modifier</v-btn>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <div v-for="(item, index) in time" :key="index">
                    {{ item }}
                </div>
            </v-col>
        </v-row>
    </v-col>

</template>

<script>
    export default {
        name: 'Task1',
        data() {
            return {
                time: [],
                modifier: 'click'
            }
        },
        methods: {
            catchTime() {
                const date = new Date()
                this.time.push(date)
            },
            changeModifier() {
                if(this.modifier === 'click'){
                    this.modifier = 'mouseover'
                }
                else {
                    this.modifier = 'click'
                }
            }
        }
    }
</script>

<style scoped>

</style>