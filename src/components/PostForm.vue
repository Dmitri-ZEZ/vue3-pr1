<template>
  <div>
    <form @submit.prevent>
      <h3>Создание поста</h3>
      <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Название поста"
      />
      <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Описание поста"
      />
      <button @click="createPost" class="btn">Создать</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
form {
  display: flex;
  flex-direction: column;
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
