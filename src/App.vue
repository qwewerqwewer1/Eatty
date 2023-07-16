<template>
  <div id="app-template">
    <form>
      <h4>Создание поста</h4>
      <input
        type="text"
        placeholder="Название"
        @input="inputValue"
        :value="title"
      />
      <input
        type="text"
        placeholder="Описание"
        @input="inputValue"
        :value="body"
      />
      <button class="btn" @click="createPost">Создать пост</button>
    </form>
    <div class="post" v-for="(post, id) in posts" :key="id">
      <div><strong>Название:</strong>{{ post.title }}</div>
      <div><strong>Описание:</strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "",
      body: "",
      posts: [
        { id: 1, title: "JavaScript 1", body: "Описание поста 1" },
        { id: 2, title: "JavaScript 2", body: "Описание поста 2" },
        { id: 3, title: "JavaScript 3", body: "Описание поста 3" },
      ],
    };
  },
  methods: {
    inputValue(e) {
      this.title = e.target.value;
    },
    createPost(obj) {},
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 5px;
  box-sizing: border-box;
}

form {
  display: flex;
  flex-direction: column;
}

input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.post {
  padding: 15px;
  border: 2px solid teal;
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