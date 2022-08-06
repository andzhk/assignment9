<template>
<div class="modal fade" :id="id" tabindex="-1" role="dialog">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header text-center">
        <h5 class="modal-title font-weight-bold text-center">{{ name }}</h5>

        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <div class="text-center">
          <img :src="image" :alt="name" />
          <p class="mt-3">
            <strong>Rating: {{ rating }}</strong>
          </p>
          <p v-html="summary"></p>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-primary text-center" data-dismiss="modal">
          <a :href="url">Visit Link</a>
        </button>
      </div>
    </div>
  </div>
</div>
</template>
<script>
export default {
  name: "ShowPopup",
  props: {
    name: {
      type: String,
      default: ""
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
    id: {
      type: Number,
      default: null
    },
    genres: {
      type: Array,
      default: () => []
    },
    image: {
      type: String,
      default: ""
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
#exampleModalCenter {
  padding-right: 0px !important;
  overflow-x: hidden;
}

.modal-open {
  padding-right: 0px !important;
}
</style>
