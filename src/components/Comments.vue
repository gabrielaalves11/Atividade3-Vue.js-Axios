<template>
  <div>
    <h6>
      4. Recupere todos os registros e mostre todos os dados dos comentários pares em
      uma lista.
    </h6>
    <button @click="fetchComments" type="button" class="btn btn-primary btn-block">Fetch Comments</button>
    <br />
    <ul>
      <li v-for="comment in comments" :key="comment.id" v-if="comment.id % 2 == 0">
        <p>
          <strong>PostId:</strong>
          {{ comment.postId }}
          <br />

          <strong>Id:</strong>
          {{ comment.id }}
          <br />

          <strong>Name:</strong>
          {{ comment.name }}
          <br />

          <strong>E-Mail:</strong>
          {{ comment.email }}
          <br />

          <strong>Body:</strong>
          {{ comment.body }}
        </p>
      </li>
      <div v-else></div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Comments",
  data() {
    return {
      comments: [],
      baseURI: "https://jsonplaceholder.typicode.com/comments",
    };
  },
  methods: {
    fetchComments: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.comments = result.data;
      });
    },
  },
};
</script>

<style>
</style>