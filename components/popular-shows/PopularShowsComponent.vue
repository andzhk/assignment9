<template>
<div>
  <h2 class="text-center font-weight-bold">Popular in this Week</h2>
  <div class="row pt-5">
    <div class="col-lg-3 col-md-3 col-sm-12 mb-4" v-for="(item, index) in popularShows" :key="index">
      <div class="img-div">
        <img :src="item.image.medium" class="img-fluid w-100 h-100" :alt="item.name" />
        <div class="summary" v-html="item.summary"></div>
      </div>

      <div class="pt-3 pb-3 card--footer">
        <h4>{{ item.name }}</h4>
        <p>Rating: {{ item.rating.average }}</p>
      </div>
    </div>
  </div>
</div>
</template>
<script>
export default {
  name: "popular-show-component",

  props: {
    popularShows: {
      type: Array,
      default: () => []
    },
  },
};
</script>
