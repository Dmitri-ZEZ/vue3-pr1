<template>
  <div class="post" v-for="post in posts">
    <div><string>Название:</string> {{ post.title }}</div>
    <div><string>Описание:</string> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
    props: {
        posts:{
            type: Array,
            required: true
        }
    }
};
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}
</style>
