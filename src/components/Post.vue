<template lang="html">
    <div class="post" v-if="post">
        <p class="title is-3">ID: {{ post.id }}</p>
        <p class="subtitle is-5">{{ post.title }}</p>
        <p class="">{{ post.body }}</p>
    </div>
</template>
<script>
import axios from 'axios';
export default {
props: ['id'],
    data() {
        return {
            post: null,
            endpoint: 'https://jsonplaceholder.typicode.com/posts/'
        }
    },
    created() {
        this.getPost(this.id)
    },

    methods: {
        getPost(id) {
            axios(this.endpoint + id)
                .then(response => {
                    this.post = response.data
                })
                .catch(error => {
                    console.log(error)
                })
        }
    }, 

    watch: {
        '$route'() {
            this.getPost(this.id);
        }
    }
}
</script>
