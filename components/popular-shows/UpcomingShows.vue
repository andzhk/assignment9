<template>
<div>
  <!-- showing upcoming shows by iterating through an array -->

  <h2 class="text-center font-weight-bold">Upcoming Shows</h2>
  <div class="row pt-5">
    <div class="col-lg-3 col-md-6 col-sm-12 mb-4" v-for="(item, index) in upcomingShowsList" :key="index">
      <div class="img-div img-div-2">
        <img :src="item.image.medium" class="img-fluid w-100 h-100" :alt="item.name" />
        <div class="summary" v-html="item.summary"></div>
      </div>
      <div class="pt-3 pb-3 card--footer">
        <h4>{{ item.name }}</h4>
        <h6>Rating: {{ item.rating.average }}</h6>
      </div>
    </div>
  </div>
</div>
</template>
<script>
export default {
  name: "upcoming-shows",
  props: {
    upcomingShowsList: {
      type: Array,
      default: () => []
    },
  },
};
</script>
