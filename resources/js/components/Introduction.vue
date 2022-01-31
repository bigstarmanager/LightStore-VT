<template>
  <div class="main-container my-10 sm:my-20 px-5 sm:px-10 py-6 sm:py-20 lg:p-20 bg-gray-100">
    <div class="grid grid-cols-1 gap-10 xl:grid-cols-2">
      <div class="flex items-start sm:items-center left-flex_section">
        <div class="flex-1 intro-text_section">
          <div
            class="
              uppercase
              font-24
              main-bold
              text-left
              xl:text-right
              text-primary
              mb-2
              technology-text
            "
          >
            Technology
          </div>
          <div
            class="
              text-left
              xl:text-right
              font-14
              main-medium
              text-gray-section
              technology-sentence
            "
          >
            Modernas maquinarias y reingeniería de productos. Estudio y
            aplicación de mejoras continuas en las metodologías de gestión y
            logística le posibilitan perfeccionar sus procesos y lograr mayor
            productividad.
          </div>
        </div>
        <div
          class="
            flex
            items-center
            xl:ml-10
            mr-5
            sm:mr-10
            justify-center
            bg-gray-300
            intro-image_box
          "
        >
          <img
            src="/dist/images/icon/intro3.png"
            alt="intro-img"
            class="intro-img"
          />
        </div>
      </div>
      <div class="flex items-start sm:items-center">
        <div
          class="
            flex
            items-center
            mr-5
            sm:mr-10
            justify-center
            bg-gray-300
            intro-image_box
          "
        >
          <img
            src="/dist/images/icon/intro2.png"
            alt="intro-img"
            class="intro-img bg-gray-300 mx-auto"
          />
        </div>
        <div class="flex-1">
          <div class="uppercase efficiency-text font-24 main-bold text-primary mb-2">
            Efficiency
          </div>
          <div class="technology-sentence font-14 main-medium text-gray-section">
            Profesionalismo en el diseño, estudio y desarrollo de nuevos
            productos privilegiando la eficiencia, óptimo rendimiento lumínico,
            estética y simplicidad en la instalación y mantenimiento, siempre a
            la vanguardia en la aplicación de las nuevas tendencias.
          </div>
        </div>
      </div>
      <div class="flex items-start sm:items-center left-flex_section">
        <div class="flex-1 intro-text_section">
          <div
            class="
              uppercase
              technology-text
              font-24
              main-bold
              text-left
              xl:text-right
              text-primary
              mb-2
            "
          >
            Quality
          </div>
          <div
            class="
              text-left
              xl:text-right
              technology-sentence
              font-14
              main-medium
              text-gray-section
            "
          >
            Una cuidada selección de materias primas y componentes, monitoreos
            intensivos en todos los procesos productivos y comprobación de la
            calidad final en productos terminados.
          </div>
        </div>
        <div
          class="
            flex
            items-center
            rounded-full
            xl:ml-10
            mr-5
            sm:mr-10
            justify-center
            bg-gray-300
            intro-image_box
          "
        >
          <img
            src="/dist/images/icon/intro1.png"
            alt="intro-img"
            class="intro-img bg-gray-300 mx-auto"
          />
        </div>
      </div>
      <div class="flex items-start sm:items-center">
        <div
          class="
            flex
            items-center
            rounded-full
            mr-5
            sm:mr-10
            justify-center
            bg-gray-300
            intro-image_box
          "
        >
          <img
            src="/dist/images/icon/intro4.png"
            alt="intro-img"
            class="intro-img bg-gray-300 mx-auto"
          />
        </div>
        <div class="flex-1">
          <div class="uppercase technology-text font-24 main-bold text-primary mb-2">
            Service
          </div>
          <div class="technology-sentence font-14 main-medium text-gray-section">
            Amplio surtido de stock. Apoyo técnico permanente y asistencia en
            los cálculos fotométricos de sus proyectos de iluminación.
            Distribuidores exclusivos en todo el país, América Latina y Europa.
            Nuestro equipo de ventas y departamento técnico están a su servicio
            para asistirlo y asesorarlo.
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Introduction",
};
</script>

<style scoped>
.intro-image_box {
  width: 130px;
  height: 130px;
  border-radius: 50%;
}
@media (max-width: 1440px) {
  .intro-image_box {
    width: 100px;
    height: 100px;
  }
}
@media (max-width: 1024px) {
  .intro-text_section {
    order: 2;
  }
}

@media (max-width: 768px) {
  .intro-image_box {
    width: 70px;
    height: 70px;
  }
  .intro-image_box img {
    width: 24px;
  }
  .technology-text, .efficiency-text {
    font-size: 18px;
  }
  .technology-sentence {
    font-size: 12px;
  }
}
</style>
