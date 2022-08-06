<template>
<div>
  <app-header />
  <nuxt />
  <app-footer />
</div>
</template>
<script>
import Vue from "vue";
import ImageMixin from "../components/imageMixin/ImageMixin";
import AppFooter from "../components/AppFooter.vue";
import AppHeader from "../components/AppHeader.vue";
import "bootstrap";
import "bootstrap/dist/css/bootstrap.css";
Vue.mixin(ImageMixin);
export default {
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>
<style lang="scss"></style>
