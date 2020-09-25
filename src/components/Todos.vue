<template>
  <div>
    <h6>
      2. Recupere e mostre todos os dados do usuário 2 e estão com status de completo em
      uma lista.
    </h6>
    <button @click="fetchTodos" type="button" class="btn btn-primary btn-block">Fetch Todos</button>
    <br />
    <ul>
      <li v-for="todo in todos" :key="todo.id" v-if="todo.userId == '2' && todo.completed == true">
        <p>
          <strong>UserId:</strong>
          {{ todo.userId }}
          <br />

          <strong>Id:</strong>
          {{ todo.id }}
          <br />

          <strong>Title:</strong>
          {{ todo.title }}
          <br />

          <strong>Completed:</strong>
          {{ todo.completed }}
        </p>
      </li>
      <div v-else></div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Todos",
  data() {
    return {
      todos: [],
      baseURI: "https://jsonplaceholder.typicode.com/todos",
    };
  },
  methods: {
    fetchTodos: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.todos = result.data;
      });
    },
  },
};
</script>

<style>
</style>