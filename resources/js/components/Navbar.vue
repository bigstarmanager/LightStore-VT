
<template>
  <nav
    class="
      main-nav
      bg-white
      text-gray-800
      flex
      main-container
      p-5
      lg:px-20
      justify-between
      items-center
      z-50
      fixed
    "
  >
    <div class="hamburger-menu_button hidden">
      <hamburger-button> </hamburger-button>
    </div>
    <a href="#">
      <div class="main--logo">
        <!-- LOGO HERE -->
        <img
          src="/dist/images/logo/navbar_logo.png"
          alt="logo_image"
          width="300px"
        />
      </div>
    </a>
    <div class="flex my-auto">
      <div class="my-auto flex">
        <div class="flex">
          <div class="my-auto mr-15 navbar-items py-3">
            <router-link
              :to="{ name: 'settings.profile' }"
              class="main-bold font-18 leading-none tracking-wide"
            >
              Projects
            </router-link>
          </div>
        </div>
        <dropdown-menu class="my-auto mr-15 navbar-items py-3">
          <div class="flex">
            <div class="my-auto mr-4">
              <p class="main-bold font-18 leading-none tracking-wide">
                Catalouge
              </p>
            </div>
          </div>

          <template v-slot:items>
            <div class="py-1">
              <router-link
                v-for="(router, index) in dropDownRouter"
                :key="index"
                :to="{ name: router.url }"
                class="
                  hover:bg-gray-200
                  main-regular
                  font-18
                  block
                  px-4
                  py-4
                  text-sm
                  leading-5
                  text-gray-900
                  focus:outline-none
                  transition-all
                  duration-100
                  ease-in-out
                  outline-none
                "
                role="menuitem"
              >
                {{ router.name }}
              </router-link>
            </div>
          </template>
        </dropdown-menu>
        <dropdown-menu class="my-auto mr-15 navbar-items py-3">
          <div class="flex">
            <div class="my-auto mr-4">
              <p class="main-bold font-18 leading-none tracking-wide">
                The Company
              </p>
            </div>
          </div>

          <template v-slot:items>
            <div class="py-1">
              <router-link
                :to="{ name: 'settings.profile' }"
                class="
                  main-regular
                  font-18
                  block
                  px-4
                  py-2
                  text-sm
                  leading-5
                  text-gray-900
                  focus:outline-none
                  transition-all
                  duration-100
                  ease-in-out
                  outline-none
                "
                role="menuitem"
              >
                Settings
              </router-link>
            </div>
            <div class="py-1">
              <span
                class="
                  main-regular
                  font-18
                  cursor-pointer
                  block
                  px-4
                  py-2
                  text-sm
                  leading-5
                  text-gray-900
                  focus:outline-none
                  transition-all
                  duration-100
                  ease-in-out
                  outline-none
                "
                role="menuitem"
              >
                Logout
              </span>
            </div>
          </template>
        </dropdown-menu>
        <button
          type="button"
          class="
            main-button
            nav-contact_btn
            main-bold
            font-12
            mr-10
            p-4
            text-white
          "
        >
          CONTACT US
        </button>
        <div class="clickable-search">
          <input
            type="search"
            class="search-input"
            placeholder="Search here ..."
          />
          <i class="fa fa-search search-icon mx-auto text-center"></i>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import { mapGetters } from "vuex";
import DropdownMenu from "./DropdownMenu";
import HamburgerButton from "./HamburgerButton.vue";

export default {
  components: { DropdownMenu, HamburgerButton},
  data: () => ({
    appName: window.config.appName,
    dropDownRouter: [
      { name: "Indoor LED Ceiling Lights", url: "settings.profile" },
      { name: "Outdoor LED Ceiling Lights", url: "settings.profile" },
      { name: "LED Street Lighting", url: "settings.profile" },
      { name: "Solar LED Fixtures", url: "settings.profile" },
      { name: "LED Industrial Pendants", url: "settings.profile" },
      { name: "Indoor LED Downlights", url: "settings.profile" },
      { name: "LED Watertight", url: "settings.profile" },
      { name: "LED Streetlights", url: "settings.profile" },
      { name: "Service Station Luminaire", url: "settings.profile" },
      { name: "LED Floodlights", url: "settings.profile" },
      { name: "LED Battens", url: "settings.profile" },
      { name: "Rail Spot", url: "settings.profile" },
    ],
  }),

  computed: mapGetters({
    user: "auth/user",
  }),

  methods: {
    async logout() {
      // Log out the user.
      await this.$store.dispatch("auth/logout");

      // Redirect to login.
      await this.$router.push({ name: "login" });
    },
  },
};
</script>
<style scoped>
.navbar-items {
  border-bottom: 3px solid transparent;
}

.navbar-items:hover {
  color: #00539f;
  border-bottom: 3px solid #00539f;
}

.clickable-search {
  position: relative;
  width: 50px;
  height: 50px;
  background: white;
  box-sizing: border-box;
  border-radius: 25px;
  border: 4px solid white;
  padding: 5px;
}

.search-input {
  position: absolute;
  top: 50px;
  left: -260px;
  width: 300px;
  height: 42.5px;
  line-height: 30px;
  outline: 0;
  box-shadow: 0px 0px 5px 1px rgba(0, 0, 0, 0.308);
  display: none;
  font-size: 1em;
  border-radius: 5px;
  padding: 0 20px;
  background: rgb(255, 255, 255);
}

.search-icon {
  box-sizing: border-box;
  padding: 30px;
  position: absolute;
  top: -20px;
  right: 0;
  color: #07051a;
  text-align: center;
  font-size: 1.5em;
}

.clickable-search:hover input {
  display: block;
}

.main-nav {
  top: 50px;
  left: 0;
  right: 0;
  z-index: 100;
}

@media (max-width: 1280px) {
  .navbar-items,
  .nav-contact_btn {
    margin-right: 30px !important;
  }
}
@media (max-width: 1024px) {
  .navbar-items,
  .nav-contact_btn {
    display: none;
  }
  .hamburger-menu_button {
    display: block !important;
    position: absolute;
  }
  .main--logo {
    margin-left: 100px;
  }
  .search-input {
    top: 0;
    left: -320px;
  }
}
@media (max-width: 768px) {
  .main--logo img {
    width: 200px;
  }
  .main--logo {
    margin-left: 60px;
  }
  .search-input {
    left: -270px;
    width: 250px;
  }
}
@media (max-width: 414px) {
  .main--logo {
    margin-left: 50px;
  }
  .search-input {
    top: 50px;
    left: -205px;
  }
  .main--logo img {
    width: 170px;
  }
  .search-icon {
    right: -20px;
  }
}
</style>
