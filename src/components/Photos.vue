<template>
  <div>
    <h6>3. Recupere e mostre todas as imagens (url) do álbum 3 em uma lista.</h6>
    <button @click="fetchPhotos" type="button" class="btn btn-primary btn-block">Fetch Photos</button>
    <br />
    <ul>
      <li v-for="photo in photos" :key="photo.id" v-if="photo.albumId == '3'">
        <p>
          <strong>AlbumId:</strong>
          {{ photo.albumId }}
          <br />

          <strong>Id:</strong>
          {{ photo.id }}
          <br />

          <strong>Title:</strong>
          {{ photo.title }}
          <br />

          <strong>Url:</strong>
          <br />
          <img :src="photo.url" width="20%" />
          <br />

          <strong>ThumbnailUrl:</strong>
          {{ photo.thumbnailUrl }}
        </p>
      </li>
      <div v-else></div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Photos",
  data() {
    return {
      photos: [],
      baseURI: "https://jsonplaceholder.typicode.com/photos",
    };
  },
  methods: {
    fetchPhotos: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.photos = result.data;
      });
    },
  },
};
</script>

<style>
</style>