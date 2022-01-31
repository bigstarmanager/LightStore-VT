<template>
  <div class="main-container px-5 lg:px-20 relative top-carousel_container">
    <button @click="showNext" class="prev-btn mr-0 lg:mr-20">
      <img src="/dist/images/carousel/pre2.png" alt="carousel-img" />
    </button>
    <button @click="showPrev" class="next-btn ml-0 lg:ml-20">
      <img src="/dist/images/carousel/next1.png" alt="carousel-img" />
    </button>
    <VueSlickCarousel ref="carousel">
      <div
        class="carousel-bg"
        v-for="(carousel, index) in carouselData"
        :key="index"
        :style="{
          background:
            'linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, #000000 100%),  url(' +
            carousel.carouselBg +
            ')',
          backgroundSize: 'cover',
          backgroundPosition: 'center',
        }"
      >
        <div
          class="
            flex
            carousel-container_box
            items-center
            pt-10
            pb-10
            px-0
            lg:px-20
          "
        >
          <div class="w-100 lg:w-3/4 pt-20 lg:px-20 top-carousel_text">
            <div class="carousel-container">
              <h1
                class="
                  font-48
                  main-bold
                  text-white
                  uppercase
                  text-center
                  xl:text-left
                  top-title-text
                "
              >
                {{ carousel.carouselTitle }}
              </h1>
              <p
                class="
                  font-regular
                  gray-text
                  carousel-descripton
                  font-22
                  pt-7
                  pb-12
                  capitalize
                  text-center
                  xl:text-left
                "
              >
                {{ carousel.carouselDescription }}
              </p>
              <button class="main-button main-bold top-carousel_btn">
                {{ carousel.carouselButton }}
              </button>
            </div>
          </div>
          <div class="w-1/4 pt-20 top-carousel_image">
            <div class="pr-20">
              <img
                class="mx-auto top-carousel_img"
                :src="carousel.carouselImage"
                alt="carousel-img"
              />
            </div>
          </div>
        </div>
      </div>
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
      {
        carouselBg: "/dist/images/carousel/background/1.jpg",
        carouselTitle: "Mega",
        carouselDescription:
          "El nuevo proyector led Mega fue diseñado para la iluminación de grandes áreas y espacios deportivos gracias a su nueva óptica que incorpora lentes haciendo que la iluminación llegue a más distancia. Cuenta con Leds de alta calidad garantizando una eficiencia máxima. Posee un diseño innovador",
        carouselImage: "/dist/images/carousel/products/p1.png",
        carouselButton: "VIEW PRODUCT",
      },
      {
        carouselBg: "/dist/images/carousel/background/2.jpg",
        carouselTitle: "AP",
        carouselDescription:
          "El nuevo proyector led Mega fue diseñado para la iluminación de grandes áreas y espacios deportivos gracias a su nueva óptica que incorpora lentes haciendo que la iluminación llegue a más distancia. Cuenta con Leds de alta calidad garantizando una eficiencia máxima. Posee un diseño innovador",
        carouselImage: "/dist/images/carousel/products/p1.png",
        carouselButton: "VIEW PRODUCT",
      },
      {
        carouselBg: "/dist/images/carousel/background/3.jpg",
        carouselTitle: "Panel",
        carouselDescription:
          "El nuevo proyector led Mega fue diseñado para la iluminación de grandes áreas y espacios deportivos gracias a su nueva óptica que incorpora lentes haciendo que la iluminación llegue a más distancia. Cuenta con Leds de alta calidad garantizando una eficiencia máxima. Posee un diseño innovador",
        carouselImage: "/dist/images/carousel/products/p1.png",
        carouselButton: "VIEW PRODUCT",
      },
    ],
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
  left: 100px;
  z-index: 10;
}
.prev-btn {
  position: absolute;
  top: 50%;
  right: 100px;
  z-index: 10;
}

.top-carousel_container {
  margin-top: 180px;
}

@media (max-width: 1440px) {
  /* .carousel-container {
    padding-left: 20px !important;
  } */
}

@media (max-width: 1024px) {
  .carousel-container_box {
    flex-direction: column;
  }
  .carousel-container_box > div {
    width: 100%;
  }
  .top-carousel_image {
    order: 1;
    padding-top: 0;
  }
  .top-carousel_image > div {
    padding-right: 0;
  }
  .top-carousel_text {
    order: 2;
    padding-left: 0;
    padding-right: 0;
    padding-top: 0;
  }
  .carousel-descripton {
    padding-right: 0;
    width: 80%;
    margin: auto;
  }
  .top-carousel_btn {
    margin: auto;
  }
  .carousel-container {
    display: flex;
    flex-direction: column;
  }
  .next-btn {
    left: 50px;
  }
  .prev-btn {
    right: 50px;
  }

  .top-carousel_img {
    width: 40%;
  }
  .top-carousel_container {
    margin-top: 155px;
  }
}
@media (max-width: 768px) {
  .top-carousel_container {
    margin-top: 140px;
  }
}
@media (max-width: 414px) {
  .prev-btn {
    right: 40px;
  }
  .next-btn {
    left: 40px;
  }
  .top-carousel_image img {
    width: 50%;
  }
  .carousel-descripton {
    font-size: 14px;
    padding: 40px 20px;
  }
  .top-title-text {
    font-size: 36px;
  }
}
</style>