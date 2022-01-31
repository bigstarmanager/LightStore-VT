<template>
  <div class="main-container footer px-5 py-10 sm:px-10 sm:py-20 lg:p-20 flex">
    <div class="footer-left w-1/3">
      <img
        src="/dist/images/logo/navbar_logo.png"
        alt="logo_image"
        width="340px"
      />
      <p class="font-14 main-medium gray-text pt-5 md:py-10 w-3/4">
        Lumenac has been present for years among the leading companies in the
        lighting market. For 37 years, it has produced and manufactured in
        Argentina a wide range of products for industrial, commercial and
        residential lighting.
      </p>
      <div>
        <p class="flex items-center font-14 main-medium gray-text my-5">
          <img
            src="/dist/images/icon/position.png"
            class="mr-3 footer-icon1"
            alt="position"
          />William Morris 567. Villa Martelli. Buenos Aires
        </p>
        <p class="flex items-center font-14 main-medium gray-text my-5">
          <img
            src="/dist/images/icon/call.png"
            class="mr-3 footer-icon2"
            alt="position"
          />4709-3300
        </p>
        <p class="flex items-center font-14 main-medium gray-text my-5">
          <img
            src="/dist/images/icon/email.png"
            class="mr-3 footer-icon3"
            alt="position"
          />SALES@LUMENAC.COM.AR
        </p>
      </div>
    </div>
    <div class="footer-center w-1/3 pl-0 md:pl-20">
      <div class="pl-0 md:pl-20">
        <p
          class="
            font-18
            main-bold
            uppercase
            text-white
            pt-10
            md:pt-0
            pb-5
            md:pb-10
            text-center
            md:text-left
          "
        >
          Navigate
        </p>
        <ul class="gray-text font-14 main-regular text-center md:text-left">
          <li class="pb-5"><a href="">Home</a></li>
          <li class="pb-5"><a href="">Projects</a></li>
          <li class="pb-5"><a href="">About Us</a></li>
          <li class="pb-5"><a href="">Contact Us</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-right w-1/3 flex">
      <div class="w-1/2 footer-right_left">
        <p
          class="
            font-18
            main-bold
            uppercase
            text-white
            pt-10
            md:pt-0
            pb-5
            md:pb-10
            text-center
            md:text-left
          "
        >
          Catalouge
        </p>
        <ul class="gray-text font-14 main-regular text-center md:text-left">
          <li class="pb-5"><a href="">Indoor LED Ceiling Lights</a></li>
          <li class="pb-5"><a href="">Outdoor LED Ceiling Lights</a></li>
          <li class="pb-5"><a href="">LED Street Lighting</a></li>
          <li class="pb-5"><a href="">Solar LED Fixtures</a></li>
          <li class="pb-5"><a href="">LED Industrial Pendants</a></li>
          <li class="pb-5"><a href="">Indoor LED Downlights</a></li>
          <li class="pb-5"><a href="">LED Watertight</a></li>
        </ul>
      </div>
      <div class="w-1/2">
        <ul
          class="gray-text font-14 pt-0 md:pt-16 main-regular text-center md:text-left"
        >
          <li class="pb-5"><a href="">LED Streetlights</a></li>
          <li class="pb-5"><a href="">Service Station Luminaire</a></li>
          <li class="pb-5"><a href="">LED Floodlights</a></li>
          <li class="pb-5"><a href="">LED Battens</a></li>
          <li class="pb-5"><a href="">Rail Spot</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
.footer {
  background: #262626;
}

.footer-icon1 {
  width: 15px !important;
  height: 18px !important;
}
.footer-icon2 {
  width: 18px !important;
  height: 18px !important;
}
.footer-icon3 {
  width: 18px !important;
  height: 14.4px !important;
}
@media (max-width: 1024px) {
  .footer-center {
    padding-left: 10px;
  }
  .footer-right {
    margin-left: -20px;
  }
  .footer-right_left {
    margin-right: 10px;
  }
}
@media (max-width: 414px) {
  .footer {
    flex-direction: column;
  }
  .footer-center,
  .footer-right,
  .footer-left {
    width: 100%;
    padding-left: 0;
  }
  .footer-left p {
    width: 100%;
  }
  .footer-right {
    flex-direction: column;
    align-items: center;
  }
  .footer-right {
    margin-left: 0px;
  }
  .footer-right_left {
    margin-right: 0px;
  }
  .footer-right > div {
    width: 100%;
  }
}
</style>
