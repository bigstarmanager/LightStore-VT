<template>
  <div class="main-container px-4 py-10 sm:px-10 sm:py-20 lg:p-20">
    <div
      class="pb-5 sm:pb-10 lg:pb-15 flex items-center justify-left lg:justify-center"
    >
      <span class="minuse-span mr-4"></span>
      <span class="uppercase font-36 main-bold latest-text">Our Latest Projects</span>
    </div>
    <div class="px-0 lg:px-20">
      <div class="flex flex-wrap justify-center project-images px-0 lg:px-20">
        <div
          v-for="(project, index) in projectData"
          :key="index"
          :style="{
            background: 'url(' + project.image + ')',
            backgroundPosition: 'center',
            backgroundRepeat: 'no-repeat',
          }"
          class="product-images"
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
              {{ project.hoverText }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="flex pt-5 sm:pt-10 lg:pt-15">
      <button class="main-button main-bold font-14 mx-auto view-text">VIEW MORE</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "LatestProject",
  data: () => ({
    projectData: [
      {
        image: "/dist/images/latest_project/1.png",
        hoverText: "FLOW 180",
      },
      {
        image: "/dist/images/latest_project/2.png",
        hoverText: "MEGA 500",
      },
      {
        image: "/dist/images/latest_project/3.png",
        hoverText: "MEGA 300-4",
      },
      {
        image: "/dist/images/latest_project/4.png",
        hoverText: "SATURNO 200",
      },
      {
        image: "/dist/images/latest_project/5.png",
        hoverText: "PARK 100",
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
  width: 400px;
  height: 300px;
  margin: 20px;
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

@media (max-width: 1280px) {
  .product-images {
    width: 300px;
    height: 200px;
    margin: 20px;
  }
}

@media (max-width: 1024px) {
  .product-images {
    margin: 10px;
  }
  .project-images {
    padding: 0;
  }
}
@media (max-width: 768px) {
  .product-images {
    width: 48%;
    height: 200px;
    margin: 1%;
  }
}
@media (max-width: 414px) {
  .product-images {
    height: 132px;
  }
  .middle p {
    font-size: 18px;
  }
  .latest-text {
    font-size: 24px;
  }
  .view-text {
    font-size: 12px;
  }
}
</style>
