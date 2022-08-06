<template>
<images :shows="shows" />
</template>
<script>
import Images from "../../components/Images.vue";
export default {
  components: {
    Images,
  },
  head() {
    return {
      title: "Shows in our Bucket - Nuxt App",
      meta: [{
        hid: "description",
        name: "description",
        content: "Best place to watch your favourite shows/movies",
      }, ],
    };
  },
  data() {
    return {
      shows: [],
    };
  },
  methods: {
    async fetchShows() {
      try {
        const response = await fetch("https://api.tvmaze.com/shows");
        const data = await response.json();
        this.shows = data.slice(0, 20);
        console.log(data);
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    this.fetchShows();
  },
};
</script>
