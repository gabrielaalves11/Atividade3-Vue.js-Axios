<template>
  <div>
    <h6>
      1. Recupere todos os registros e mostre todos os dados apenas dos 5 primeiros em
      uma lista.
    </h6>
    <button @click="fetchUsers" type="button" class="btn btn-primary btn-block">Fetch Users</button>
    <br />
    <ul>
      <li v-for="(user, i) in users" :key="user.id" v-if="i < 5">
        <p>
          <strong>Id:</strong>
          {{ user.id }}
          <br />

          <strong>Name:</strong>
          {{ user.name }}
          <br />

          <strong>Username:</strong>
          {{ user.username }}
          <br />

          <strong>E-Mail:</strong>
          {{ user.email }}
          <br />

          <strong>Address:</strong>
          <br />
          Street: {{ user.address.street }}
          <br />
          Suite: {{ user.address.suite }}
          <br />
          City: {{ user.address.city }}
          <br />
          Zipcode: {{ user.address.zipcode }}
          <br />
          <strong>Geo:</strong>
          <br />
          Lat: {{ user.address.geo.lat }}
          <br />
          Lng: {{ user.address.geo.lng }}
          <br />

          <strong>Phone:</strong>
          {{ user.phone }}
          <br />

          <strong>Website:</strong>
          {{ user.website }}
          <br />

          <strong>Company:</strong>
          <br />
          Name: {{ user.company.name }}
          <br />
          CatchPhrase: {{ user.company.catchPhrase }}
          <br />
          bs: {{ user.company.bs }}
        </p>
      </li>
      <div v-else></div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Users",
  data() {
    return {
      users: [],
      baseURI: "https://jsonplaceholder.typicode.com/users",
    };
  },
  methods: {
    fetchUsers: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.users = result.data;
      });
    },
  },
};
</script>

<style>
</style>