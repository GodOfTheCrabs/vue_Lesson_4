<!-- 9.Виведіть довгий список елементів з пагінацією, використовуючи v-for, і динамічно змінюйте відображені елементи при кліку на кнопки пагінації. -->

<template>
    <div style="width: 900px; margin: 0 auto" class="task-border">
        <p class="h4">Task 9</p>
        <div>
            <v-btn 
                v-for="page in totalPage()" 
                :key="page" 
                @click="changePage(page)"
                variant="outlined"
                style="margin-left: 5px;"
                :class="{ active: currentPage === page }"
            >
                {{page}}
            </v-btn >
        </div>
        <v-row>
            <v-col cols="12" md="4" v-for="post in getLimitItems()" :key="post.id">
                <Post :post="post"/>
            </v-col>  
        </v-row>
    </div>
</template>

<script>    
    import axiosIntance from '../../services/axios.js';
    import Post from '../components/Post.vue';

    export default {
        name: 'Task9',
        components: {
            Post
        },
        data() {
            return {
                posts: [],
                currentPage: 1,
                itemLimit: 9
            }
        },
        methods: {
            getPosts() {
                axiosIntance.get('/posts')
                    .then(response => {
                        this.posts = response.data
                        console.log(response.data)
                    })
                    .catch(error => {
                        console.log(error)
                    })
            },
            totalPage() {
                return Math.ceil(this.posts.length / this.itemLimit)
            },
            getLimitItems() {
                const start = (this.currentPage - 1) * this.itemLimit
                const end = start + this.itemLimit
                return this.posts.slice(start, end)
            },
            changePage(page) {
                this.currentPage = page
            }
        },
        mounted() {
            this.getPosts()
        }
    }

</script>

<style lang="css" scoped>
    .active {
        background-color: #007bff;
        color: white;
    }
</style>