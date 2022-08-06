<template>
<div>
  <show-popup v-if="show" :name="name" :image="image" :summary="summary" :genres="genres" :url="url" :id="id" :rating="rating" />
  <div class="show-card">
    <img :src="image" :alt="alt" class="img-fluid w-100 h-100 border border-dark rounded cursor-pointer" data-toggle="tooltip" data-placement="top" :title="name" />
    <div class="overlay-section">
      <h4 class="font-weight-bold">{{ name }}</h4>
      <p>Rating: {{ rating }}</p>
      <div class="genres">
        <span v-for="(item, index) in genres" :key="index">{{ item }}</span>
      </div>
      <button class="btn btn-success mt-3" data-toggle="modal" :data-target="'#' + id" @click="showModal">
        Read More
      </button>
    </div>
  </div>
</div>
</template>
<script>
import ShowPopup from "../images-components/showPopup.vue";
export default {
  name: "ThumbnailImages",
  components: {
    ShowPopup,
  },
  props: {
    image: {
      type: String,
      default: ""
    },
    alt: {
      type: String,
      default: ""
    },
    name: {
      type: String,
      default: ""
    },
    id: {
      type: Number,
      default: null
    },
    summary: {
      type: String,
      default: ""
    },
    rating: {
      type: Number,
      default: null
    },
    url: {
      type: String,
      default: ""
    },
    genres: {
      type: Array,
      default: () => []
    },
  },
  data() {
    return {
      show: false,
    };
  },
  methods: {
    showModal() {
      this.show = true;
    },
  },
};
</script>

<style scoped>
.image-border {
  border: 6px solid rgb(182, 209, 28) !important;
}

.cursor-pointer {
  cursor: pointer;
}

.show-card {
  position: relative;
}

.overlay-section {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 1.5rem;
  background: rgba(0, 0, 0, 0.753);
  color: white;
}

.genres {
  display: flex;
}

.genres span {
  margin-right: 10px;
  display: inline-block;
}
</style>
