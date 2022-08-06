<template>
<div class="container-fluid pt-5 pb-5">
  <div class="container">
    <div class="btns-div d-flex m-auto justify-content-center">
      <!-- button on click of it, we can show "popular shows" -->

      <button @click="showPopularShows" type="button" class="btn btn-primary m-3">
        Popular Shows
      </button>

      <!-- button on click of it, we can show "upcoming shows" -->
      <button @click="showUpcomingShows" type="button" class="btn btn-primary m-3">
        Upcoming Shows
      </button>
    </div>
  </div>
  <div class="container pt-5">
    <!-- rendering upcoming and popuplar shows on the basis of conditions using v-if v-else-->

    <upcoming-shows v-if="upcomingShows" :upcomingShowsList="upcomingShowsList" />
    <popular-show-component v-else :popularShows="popularShows" />
  </div>
</div>
</template>
<script>
import PopularShowComponent from "../../components/popular-shows/PopularShowsComponent.vue";
import UpcomingShows from "../../components/popular-shows/UpcomingShows.vue";
export default {
  name: "popular-shows",
  components: {
    PopularShowComponent,
    UpcomingShows
  },
  data() {
    return {
      upcomingShows: false,
      popularShows: [],
      upcomingShowsList: [],
    };
  },
  head() {
    return {
      title: "Popular and Upcoming Shows - Nuxt App",
      meta: [{
        hid: "description",
        name: "description",
        content: "Best place to watch your favourite shows/movies",
      }, ],
    };
  },
  methods: {
    showPopularShows() {
      this.upcomingShows = false;
    },
    showUpcomingShows() {
      this.upcomingShows = true;
    },
    async fetchShows() {
      try {
        const response = await fetch("https://api.tvmaze.com/shows");
        const data = await response.json();
        this.popularShows = data.slice(20, 26);
        this.upcomingShowsList = data.slice(30, 45);
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
<style scoped></style>
