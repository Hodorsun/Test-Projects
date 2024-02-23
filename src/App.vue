<template>
    <div class="app">
       <post-form
                  @create="createPost"/>
       <post-list 
                 :posts="posts"/>
    </div>
</template>

<script>
    import PostForm from '@/components/PostForm';
    import PostList from '@/components/PostList';
    export default {
        components: {
            PostList, PostForm
        },
        data() {
            return {
                posts: [
                    { id: 1, title: 'Javascript', body: 'description of the post' },
                    { id: 2, title: 'Javascript 2', body: 'description of the post 2' },
                    { id: 3, title: 'Javascript 3', body: 'description of the post 3' },
                ],
            }
        },
        methods: {
            createPost(post) {
                this.posts.push(post);
            }
        }
    }
</script>

<style>
* {
  margin: 0;
  padding: 0;
} 

.app{
    padding: 20px;
}
</style>