<template>
    <form @submit.prevent>
        <h4>Create new post:</h4>
        <input 
               v-model="post.title"
               class="input"
               type="text"
               placeholder="Name">
        <input 
               v-model="post.body"
               class="input"
               type="text"
               placeholder="Description">
        <button 
               class="btn"
                @click="createPost">
               Press to add new!
        </button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                post: {
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost() {
                this.post.id = Date.now();
                this.$emit('create', this.post)
                this.post = {
                    title: '',
                    body: ''
                }
            }
        }
    }

</script>

<style scoped>
    form {
        display: flex;
        flex-direction: column;
    }

    .input {
        width: 100%;
        border: 1px solid teal;
        padding: 10px 15px;
        margin-top: 15px;
    }

    .btn {
        margin-top: 15px;
        align-self: flex-end;
        padding: 10px 15px;
        background: none;
        color: teal;
        border: 1px solid teal;
    }
</style>