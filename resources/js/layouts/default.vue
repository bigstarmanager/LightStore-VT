<template>
  <div>
    <topbar />
    <navbar />
    <top-carousel />
    <product-carousel />
    <product-gallery />
    <who-section />
    <introduction />
    <latest-project />
    <contact />
    <footer-component />
    <copywrite />
  </div>
</template>

<script>
import Navbar from "~/components/Navbar";
import Contact from "../components/Contact.vue";
import Copywrite from '../components/Copywrite.vue';
import FooterComponent from '../components/FooterComponent.vue';
import Introduction from "../components/Introduction.vue";
import LatestProject from "../components/LatestProject.vue";
import ProductCarousel from "../components/ProductCarousel.vue";
import ProductGallery from "../components/ProductGallery.vue";
import Topbar from "../components/Topbar";
import TopCarousel from "../components/TopCarousel.vue";
import WhoSection from "../components/WhoSection.vue";

export default {
  name: "MainLayout",
  components: {
    Navbar,
    Topbar,
    TopCarousel,
    ProductCarousel,
    ProductGallery,
    WhoSection,
    Introduction,
    LatestProject,
    Contact,
    FooterComponent,
    Copywrite,
  },
};
</script>