<template>
  <div>
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input type="text" placeholder="Название" v-model="title" />
      <input type="text" placeholder="Описание" v-model="body" />
      <button class="btn" @click="createPost">Создать пост</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "",
      body: "",
    };
  },
  methods: {
    createPost() {
      let post = {
        title: this.title,
        body: this.body,
        id: Date.now(),
      };
      this.$emit("create", post);
      this.title = "";
      this.body = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

input {
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>