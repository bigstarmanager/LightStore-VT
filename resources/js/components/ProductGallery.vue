<template>
  <div class="py-10 sm:py-20 main-container">
    <div class="px-5 sm:px-10 lg:px-20">
      <div
        class="pb-10 sm:pb-15 product-carousel_title flex items-center justify-between"
      >
        <div class="flex items-center">
          <span class="minuse-span mr-4"></span>
          <span class="uppercase font-36 main-bold categori-text">Categories</span>
        </div>
        <div class="flex items-center pointer">
          <span class="uppercase text-red hidden sm:inline-box font-18 main-bold mr-2"
            >View all</span
          >
          <img class="hidden sm:inline-box" src="/dist/images/icon/arrow.png" alt="arrow-img" />
        </div>
      </div>
    </div>
    <div class="px-5 sm:px-10 lg:px-0 grid grid-cols-2 lg:grid-cols-4">
      <div
        v-for="(gallery, index) in galleryData"
        :key="index"
        :style="{
          background: 'url(' + gallery.image + ')',
          height: 480 + 'px',
          backgroundPosition: 'center',
          backgroundRepeat: 'no-repeat',
        }"
        class="product-images w-100"
      >
        <div class="middle flex items-center">
          <p
            class="
              text-center
              mx-auto
              uppercase
              font-36
              w-3/4
              main-bold
              text-white
            "
          >
            {{ gallery.text }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
 
<script>
export default {
  name: "ProductGallery",
  data: () => ({
    galleryData: [
      {
        image: "/dist/images/gallery/1.png",
        text: "ALUMBRADO PUBLICO",
      },
      {
        image: "/dist/images/gallery/2.png",
        text: "ARTEFACTOS SOLARES LED",
      },
      {
        image: "/dist/images/gallery/3.png",
        text: "Colgantes Industriales LED",
      },
      {
        image: "/dist/images/gallery/4.png",
        text: "Empotrables LED",
      },
      {
        image: "/dist/images/gallery/5.png",
        text: "Estancos LED",
      },
      {
        image: "/dist/images/gallery/6.png",
        text: "Plafones LED de exterior",
      },
      {
        image: "/dist/images/gallery/7.png",
        text: "Protectores LED",
      },
      {
        image: "/dist/images/gallery/8.png",
        text: "Regletas LED",
      },
    ],
  }),
};
</script> 
<style scoped>
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

@media (max-width: 1440px) {
  .product-images {
    height: 360px !important;
  }
}
@media (max-width: 1280px) {
  .product-images {
    height: 320px !important;
  }
}
@media (max-width: 1024px) {
  .product-images {
    height: 256px !important;
  }
}
@media (max-width: 768px) {
  .product-images {
    height: 344px !important;
  }
}
@media (max-width: 414px) {
  .product-images {
    height: 189px !important;
  }
  .middle p {
    font-size: 18px;
    width: 90%;
  }
  .categori-text {
    font-size: 24px !important;
  }
}
</style>