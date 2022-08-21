<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list v-bind:posts="posts"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "post1", body: "body1" },
        { id: 2, title: "post2", body: "body2" },
        { id: 3, title: "post3", body: "body3" },
        { id: 3, title: "post3", body: "body3" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>
