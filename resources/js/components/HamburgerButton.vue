<template>
  <div id="menuToggle">
    <input type="checkbox" />
    <span></span>
    <span></span>
    <span></span>
    <div class="" id="menu">
      <div>
        <div class="flex navbar-items">
          <div class="mx-auto">
            <router-link
              :to="{ name: 'settings.profile' }"
              class="
                main-bold
                font-24
                menu-title_text
                leading-none
                tracking-wide
              "
            >
              Projects
            </router-link>
          </div>
        </div>
        <div class="flex navbar-items">
          <hamburger-dropdown class="mx-auto py-3">
            <div class="">
              <div class="my-auto mr-4">
                <p
                  class="
                    main-bold
                    font-24
                    leading-none
                    menu-title_text
                    tracking-wide
                  "
                >
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
                    font-14
                    sm:font-24
                    block
                    py-4
                    text-center text-sm
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
          </hamburger-dropdown>
        </div>
        <div class="flex navbar-items">
          <hamburger-dropdown class="mx-auto py-3">
            <div class="">
              <div class="my-auto mr-4">
                <p
                  class="
                    main-bold
                    font-24
                    leading-none
                    menu-title_text
                    tracking-wide
                  "
                >
                  The Company
                </p>
              </div>
            </div>

            <template v-slot:items>
              <div class="py-1">
                <router-link
                  v-for="(router, index) in dropDownRouter1"
                  :key="index"
                  :to="{ name: router.url }"
                  class="
                    hover:bg-gray-200
                    main-regular
                    font-14
                    sm:font-24
                    block
                    py-4
                    text-center text-sm
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
          </hamburger-dropdown>
        </div>
        <div class="flex navbar-items contact-button">
          <button
            type="button"
            class="
              main-button
              nav-contact_btn
              main-bold
              font-14
              sm:font-24
              mx-auto
              p-4
              text-white
            "
          >
            CONTACT US
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapGetters } from "vuex";
import HamburgerDropdown from "./HamburgerDropdown.vue";
export default {
  components: { HamburgerDropdown },
  name: "HamburgerButton",
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
    dropDownRouter1: [
      { name: "Indoor LED Ceiling Lights", url: "settings.profile" },
      { name: "Outdoor LED Ceiling Lights", url: "settings.profile" },
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
#menuToggle {
  /* display: block; */
  position: relative;
  top: 12px;
  left: 0px;
  z-index: 1;
  -webkit-user-select: none;
  user-select: none;
}

#menuToggle a {
  text-decoration: none;
  color: #232323;
  transition: color 0.3s ease;
}

#menuToggle input {
  display: block;
  width: 40px;
  height: 32px;
  position: absolute;
  top: -7px;
  left: -5px;
  cursor: pointer;
  opacity: 0; /* hide this */
  z-index: 2; /* and place it over the hamburger */
  -webkit-touch-callout: none;
}

#menuToggle span {
  display: block;
  width: 60px;
  height: 8px;
  margin-bottom: 10px;
  position: relative;

  background: black;
  border-radius: 3px;

  z-index: 1;

  transform-origin: 4px 0px;

  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
}

#menuToggle span:first-child {
  transform-origin: 0% 0%;
}

#menuToggle span:nth-last-child(2) {
  transform-origin: 0% 100%;
}

#menuToggle input:checked ~ span {
  opacity: 1;
  transform: rotate(45deg) translate(-2px, -1px);
  background: #232323;
}

#menuToggle input:checked ~ span:nth-last-child(3) {
  opacity: 0;
  transform: rotate(0deg) scale(0.2, 0.2);
}

#menuToggle input:checked ~ span:nth-last-child(2) {
  transform: rotate(-45deg) translate(0, -1px);
}

#menu {
  position: absolute;
  width: 100vw;
  height: 500px;
  overflow: auto;
  top: 65px;
  left: -80px;
  padding: 0 50px 50px 50px;
  background: white;
  list-style-type: none;
  -webkit-font-smoothing: antialiased;
  transform-origin: 0% 0%;
  transform: translate(-100%, 0);
  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
}

#menuToggle input:checked ~ #menu {
  transform: none;
}

.navbar-items {
  padding: 20px 0;
  border-top: 2px solid #00000040;
}

@media (max-width: 768px) {
  #menu {
    left: -20px;
    top: 50px;
    height: 900px;
  }
  #menuToggle span {
    width: 40px;
    height: 4px;
    margin-bottom: 8px;
    border-radius: 5px;
  }
  #menuToggle {
    top: 5px;
  }
}
@media (max-width: 414px) {
  #menuToggle span {
    width: 35px;
    height: 4px;
    margin-bottom: 6px;
    border-radius: 5px;
  }
  #menuToggle {
    top: 4px;
  }

  #menu {
    left: -20px;
    height: 620px;
  }
  .menu-title_text {
    font-size: 18px;
  }
  .navbar-items {
  padding: 10px 0;
}
}
</style>
