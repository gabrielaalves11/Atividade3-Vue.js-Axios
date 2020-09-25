<template>
  <div>
    <h6>
      5. Recupere todos os registros e mostre todos os dados dos posts ímpares em uma
      lista.
    </h6>
    <button @click="fetchPosts" type="button" class="btn btn-primary btn-block">Fetch Posts</button><br>
    <ul>
      <li v-for="post in posts" :key="post.id" v-if="post.id % 2 == 1">
          <p>
          <strong>UserId:</strong>
          {{ post.userId }}
          <br />

          <strong>Id:</strong>
          {{ post.id }}
          <br />

          <strong>Title:</strong>
          {{ post.title }}
          <br />

          <strong>Body:</strong>
          {{ post.body }}
        </p>
      </li>
      <div v-else></div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Posts",
  data() {
    return {
      posts: [],
      baseURI: "https://jsonplaceholder.typicode.com/posts",
    };
  },
  methods: {
    fetchPosts: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.posts = result.data;
      });
    },
  },
};
</script>

<style>
</style>