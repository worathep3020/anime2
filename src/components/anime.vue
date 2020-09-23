<template>
  <div>
    <input type="text" v-model="textSearch " placeholder="Search Anime!!!" />
    <button @click="searchData()" class="btn-outline-secondary "><i class="fa fa-search"></i></button>
    <br />
    <br />
    <b-card-group columns>
      <b-card
        v-for="data in List"
        :key="data.mal_id"
        :title="data.title"
        :img-src="data.image_url"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="alert alert-secondary"
      >
        <b-card-text>{{data.synopsis}}</b-card-text>
        <b-button :href="data.url" variant="dark">Go</b-button>
      </b-card>
    </b-card-group>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      List: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get(
          "https://api.jikan.moe/v3/search/anime?q=" + this.textSearch + "page1"
        )
        .then((response) => {
          this.List = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
</style>