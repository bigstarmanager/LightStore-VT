<template>
  <div class="relative carousel-div">
    <div class="border border-black double-border"></div>
    <VueSlickCarousel ref="carousel" v-bind="settings">
      <img
        class="carousel-bg"
        v-for="(carousel, index) in carouselData"
        :key="index"
        :src="carousel"
        alt="grid-img"
        width="480px"
        height="480px"
      />
    </VueSlickCarousel>
  </div>
</template>
 
<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  name: "TopCarousel",
  components: { VueSlickCarousel },
  data: () => ({
    carouselData: [
      "/dist/images/new/1.png",
      "/dist/images/new/2.png",
      "/dist/images/new/3.png",
    ],
    settings: {
      infinite: true,
      autoplay: true,
      speed: 1000,
      autoplaySpeed: 2000,
      dots: false,
      arrows: false,
    },
  }),
};
</script> 
<style scoped>
.carousel-div {
  width: 100%;
  height: 100%;
}
.double-border {
  position: absolute;
  height: 100%;
  width: 100%;
  top: 20px;
  left: 20px;
}

.carousel-bg {
  filter: grayscale(100%);
}
.carousel-bg:hover {
  filter: grayscale(0);
}
@media (max-width: 414px) {
  .carousel-div {
    width: 90% !important;
    height: 90% !important;
    margin: auto;
  }
  .double-border {
    height: 100%;
    width: 100%;
    top: 15px;
    left: 15px;
  }
}
</style>