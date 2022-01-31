<template>
  <div class="main-container px-5 py-10 sm:p-10 lg:p-20">
    <div class="pb-0 sm:pb-15 product-carousel_title flex items-center">
      <div class="w-2/3">
        <div class="flex items-center">
          <span class="minuse-span mr-4"></span>
          <span class="uppercase who-text font-36 main-bold">who we are?</span>
        </div>
        <div
          class="
            pt-7
            pb-12
            main-medium
            text-gray-section
            font-18
            text-sentence
            w-100
            lg:w-3/4
          "
        >
          Lumenac has been present for years among the leading companies in the
          lighting market. For 37 years, it has produced and manufactured in
          Argentina a wide range of products for industrial, commercial and
          residential lighting. The products that Lumenac offers are
          manufactured in its two production plants located in the town of Villa
          Martelli, Buenos Aires.
        </div>
        <button class="main-button font-14 main-bold hidden lg:block">
          READ MORE
        </button>
      </div>
      <div class="w-1/3">
        <who-carousel />
      </div>
      <button class="main-button font-14 mt-10 sm:mt-15 main-bold lg:hidden">READ MORE</button>
    </div>
  </div>
</template>

<script>
import WhoCarousel from "./WhoCarousel.vue";
export default {
  name: "WhoSection",
  components: { WhoCarousel },
};
</script>

<style scoped>
@media (max-width: 768px) {
  .product-carousel_title {
    flex-direction: column;
  }
  .product-carousel_title > div {
    width: 100%;
  }
}
@media (max-width: 414px) {
  .who-text {
    font-size: 24px;
  }
  .text-sentence {
    font-size: 14px;
  }
  .main-button {
    font-size: 12px;
  }
}
</style>
