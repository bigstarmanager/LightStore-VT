<template>
  <div
    class="
      main-container
      px-5
      sm:px-10
      py-10
      sm:py-20
      lg:p-20
      bg-gray-200
      flex
      contact-section
      justify-between
      items-center
    "
  >
    <div class="w-1/3">
      <p
        class="contact-title uppercase font-36 pb-5 main-bold text-black"
        style="color: #1a1a1a"
      >
        Contact Us
      </p>
      <p
        class="
          contact-description
          font-18
          main-medium
          capitalize
          text-gray-section
        "
      >
        Do you need help with some of our products? Feel free to write to us and
        an advisor will contact you soon!
      </p>
    </div>
    <div class="w-1/3 mt-5 xl:mt-0 ">
      <button class="main-button contact-button contact-title font-36 main-bold flex items-center">
        <img
          src="/dist/images/icon/contact.png"
          class="mr-5 contact-img"
          alt="contact-img"
        />
        4709-3300
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
};
</script>

<style scoped>
@media (max-width: 1024px) {
  .contact-section {
    display: block;
  }
  .contact-section div {
    width: 100%;
  }
  .contact-button {
    margin-top: 30px;
    margin: auto;
  }
}
@media (max-width: 414px) {
  .contact-img {
    width: 24px;
  }
  .contact-title {
    font-size: 24px;
  }
  .contact-description {
    font-size: 14px;
  }
}
</style>
