<template>
  <div class="main-container px-5 sm:px-10 lg:px-20 py-10 sm:py-20 realtive">
    <div
      class="
        pb-5
        md:pb-15
        product-carousel_title
        flex
        items-center
        justify-center
        relative
      "
    >
      <span class="minuse-span mr-4"></span>
      <span class="uppercase font-36 main-bold product-text">new Products</span>
      <button
        class="
          bg-primary
          absolute
          contracto-button
          rounded-lg
          main-bold
          font-14
          flex
          items-center
          justify-between
        "
      >
        <p class="invisible hidden-text">ACTO</p>
        <p class="hidden-text font-14 main-bold">CONTACTO</p>
        <img
          class="ml-5"
          src="/dist/images/icon/message.png"
          alt="message-img"
        />
      </button>
    </div>
    <div class="relative">
      <button @click="showNext" class="prev-btn">
        <img src="/dist/images/carousel/next2.png" alt="carousel-img" />
      </button>
      <button @click="showPrev" class="next-btn">
        <img src="/dist/images/carousel/pre3.png" alt="carousel-img" />
      </button>
      <VueSlickCarousel v-bind="settings" ref="carousel">
        <div
          v-for="(carousel, index) in carouselData"
          :key="index"
          :style="{
            background: 'url(' + carousel + ')',
            height: 282 + 'px',
            backgroundPosition: 'center',
            backgroundRepeat: 'no-repeat',
            backgroundSize: 'contain',
          }"
          class="product-images"
        >
          <div class="middle flex items-center">
            <p
              class="text-center mx-auto uppercase font-24 main-bold text-white"
            >
              LED <br />
              Floodlisghts
            </p>
          </div>
        </div>
      </VueSlickCarousel>
    </div>
  </div>
</template>
 
<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  name: "ProductCarousel",
  components: { VueSlickCarousel },
  data: () => ({
    carouselData: [
      "/dist/images/carousel/product-carousel/1.png",
      "/dist/images/carousel/product-carousel/2.png",
      "/dist/images/carousel/product-carousel/3.png",
      "/dist/images/carousel/product-carousel/4.png",
      "/dist/images/carousel/product-carousel/5.png",
      "/dist/images/carousel/product-carousel/3.png",
    ],
    settings: {
      infinite: true,
      slidesToShow: 5,
      slidesToScroll: 1,
      initialSlide: 0,
      dots: false,
      responsive: [
        {
          breakpoint: 1024,
          settings: {
            slidesToShow: 3,
            slidesToScroll: 1,
            infinite: true,
          },
        },
        {
          breakpoint: 768,
          settings: {
            slidesToShow: 2,
            slidesToScroll: 1,
            initialSlide: 2,
          },
        },
        {
          breakpoint: 480,
          settings: {
            slidesToShow: 2,
            slidesToScroll: 1,
          },
        },
      ],
    },
  }),
  methods: {
    showNext() {
      this.$refs.carousel.next();
    },
    showPrev() {
      this.$refs.carousel.prev();
    },
  },
};
</script> 
<style scoped>
.next-btn {
  position: absolute;
  top: 50%;
  left: 20px;
  z-index: 10;
}
.prev-btn {
  position: absolute;
  top: 50%;
  z-index: 10;
  right: 20px;
}
.carousel-descripton {
  line-height: 27px;
}

.contracto-button {
  right: -50px;
  color: white;
  padding: 15px 10px;
}

.product-images {
  transition: 0.5s ease;
  backface-visibility: hidden;
  position: relative;
}

.middle {
  transition: 0.5s ease;
  opacity: 0;
  background: rgba(26, 26, 26, 0.75);
  width: 100%;
  height: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  text-align: center;
}
.product-images:hover .middle {
  opacity: 1;
}
@media (max-width: 768px) {
  .product-carousel_title {
    justify-content: left;
  }
  .contracto-button {
    right: -20px;
  }
}
@media (max-width: 414px) {
  .hidden-text {
    display: none;
  }
  .contracto-button img {
    margin: 0 10px;
  }
  .contracto-button {
    top: 100px;
    z-index: 20;
  }
  .product-images {
    height: 130px !important;
  }
  .prev-btn {
    right: 0;
  }
  .next-btn {
    left: 0;
  }
  .middle {
    width: 80%;
  }
  .product-text {
    font-size: 24px;
  }
  .middle p {
    font-size: 12px;
  }
}
</style>