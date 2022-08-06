<template>
<div>
  <!-- navigation menu -->

  <nav class="container-fluid navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand mt-2" href="/">NuxtApp</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item active">
          <nuxt-link class="nav-link" to="/">Home</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/shows">Shows</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/popular-shows">Popular Shows</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/faqs">FAQs</nuxt-link>
        </li>
      </ul>
    </div>
  </nav>
</div>
</template>
<script>
export default {
  name: "AppHeader",
};
</script>
