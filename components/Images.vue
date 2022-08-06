<template>
<!-- images component -->

<div>
  <!-- a large image just to show make a good UI -->
  <h1 class="text-center display-4 mt-5 font-weight-bold">
    Shows in Our Bucket!
  </h1>
  <div class="container-fluid pt-5 pb-5">
    <div class="container">
      <!-- iterating through an image array and displaying images on UI -->

      <div class="row">
        <div class="col-sm-6 col-lg-3 col-md-4 mb-4" v-for="(item, index) in shows" :key="index">
          <thumbnail-images :image="item.image.medium" :alt="item.name" :name="item.name" :id="item.id" :summary="item.summary" :rating="item.rating.average" :url="item.url" :genres="item.genres"></thumbnail-images>
        </div>
      </div>
      <p class="pt-4 pb-4">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Optio
        ratione nihil quas dicta assumenda culpa minima, non praesentium
        repudiandae pariatur quam voluptatibus magni laudantium, libero
        deserunt nostrum eius expedita quos explicabo! Quo, doloremque!
        Dignissimos error molestias dolor facere accusantium ducimus
        laudantium magni qui vitae quod, veniam facilis alias ea delectus
        culpa temporibus consectetur praesentium, assumenda sapiente
        inventore. Quisquam dolore, repellendus autem sint veritatis odio
        incidunt reprehenderit eligendi blanditiis totam fugiat accusantium
        vero natus sapiente libero sit quae? Corporis cupiditate quod
        voluptate impedit ipsum tenetur magni recusandae quasi at itaque?5
        Praesentium eius eaque molestiae libero excepturi quod ex ad illo
        tempore.
      </p>
    </div>
  </div>
</div>
</template>
<script>
import image3 from "~/assets/images/image3.webp";
import LargeImage from "./images-components/LargeImage.vue";
import ThumbnailImages from "./images-components/ThumbnailImages.vue";
export default {
  name: "images-page",
  components: {
    LargeImage,
    ThumbnailImages,
  },
  props: {
    shows: {
      type: Array,
      default: () => []
    },
  },
  data() {
    return {
      // images array
      largeImage: image3,
    };
  },
};
</script>
