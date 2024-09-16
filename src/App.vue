<template>
  <div class="container" style="width: 1000px; margin: 0 auto" :class="isDarkTheme ? 'dark-theme' : 'light-theme'">
    <Task1 />
    <Task2 />
    <Task4 />
    <Task5 />
    <!-- 6.Створіть переключатель тем, який динамічно змінює стилі всього додатку між темною та світлою темами. -->
    <div class="task-border">
      <p class="h4">Task 6</p>
      <v-btn variant="outlined" @click="changeTheme">Change theme</v-btn>
    </div>
    <Task7 />
    <Task8 />
    <Task9 />
    <Task10 />
  </div>
</template>

<script>
import Task1 from '@/components/Task1.vue'
import Task2 from '@/components/Task2.vue'
import Task4 from '@/components/Task4.vue'
import Task5 from '@/components/Task5.vue'
import Task7 from '@/components/Task7.vue'
import Task8 from '@/components/Task8.vue'
import Task9 from '@/components/Task9.vue'
import Task10 from '@/components/Task10.vue'


export default {
  name: 'App',
  components: {
    Task1,
    Task2,
    Task4,
    Task5,
    Task7,
    Task8,
    Task9,
    Task10
  },
  data() {
    return {
      isDarkTheme: false,
    }
  },
  methods: {
    changeTheme() {
      this.isDarkTheme = !this.isDarkTheme
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.dark-theme {
  background-color: #2c3e50;
  color: white;
}

.light-theme {
  background-color: white;
  color: #2c3e50;
}

.task-border {
    border: 1px solid black;
    border-radius: 10px;
    padding: 10px;
    margin-top: 25px;
    display: inline-block;
}
.container {
    display: flex;
    flex-direction: column;
    align-items: center
}

</style>
