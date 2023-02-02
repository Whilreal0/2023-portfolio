<template>
  <div
    class="fixed z-10 bg-[#ECF9FF] w-full top-0 transition duration-300 ease-in"
    :class="{ 'md:sticky': isSticky, 'md:drop-shadow-md': isSticky }"
  >
    <!-- this is for pc -->
    <div class="px-3 md:px-5 hidden md:block">
      <header
        class="
          w-full
          flex
          items-center
          justify-between
          h-16
          max-w-[61rem]
          px-3
          md:px-5
          mx-auto
        "
      >
        <strong> <a href="/">WHILREAL</a></strong>
        <nav>
          <ul class="flex gap-5 justify-center items-center">
            <li
              class="hover:font-bold transition duration-300 ease-in-out"
              v-for="item in scrollLgNav"
              :key="item.label"
              @click.prevent="item.scroll"
            >
              <a href="">{{ item.label }}</a>
            </li>
          </ul>
        </nav>
      </header>
    </div>
    <!--  -->
    <!-- small-screen -->
    <div
      id="navSmall"
      :class="{ 'drop-shadow-md': isSticky }"
      class="
        absolute
        top-0
        z-[99999]
        flex
        justify-between
        items-center
        md:hidden
        bg-[#ECF9FF]
        w-full
        py-2
        px-[22px]
        md:px-0
      "
    >
      <h1>whil</h1>
      <button
        v-if="!isOpen"
        @click.prevent="openNav"
        class="flex items-center px-1.5 py-1 rounded shadow-md bg-transparent"
      >
        <box-icon class="fill-[#f77e1c]" name="menu"></box-icon>
      </button>
      <button
        v-else
        @click.prevent="openNav"
        class="flex items-center px-1.5 py-1 rounded shadow-md bg-transparent"
      >
        <box-icon class="fill-[#f77e1c]" name="x"></box-icon>
      </button>
    </div>
    <!-- small-screen -->
    <!-- mobile menu -->
    <div
      v-if="isOpen"
      @click="openNav"
      class="bg-black opacity-50 absolute h-screen w-full md:hidden"
    ></div>
    <transition
      enter-active-class="animate__animated animate__fadeInLeft"
      leave-active-class="animate__animated animate__fadeOutLeft"
    >
      <div
        class="
          md:hidden
          absolute
          top-[48px]
          flex
          gap-2
          justify-center
          w-screen
          p-2
          bg-[#d1eefc]
          transition
          duration-500
        "
        v-show="isOpen"
      >
        <button
          class="uppercase text-sm font-semibold py-1 px-1.5 rounded-md"
          v-for="navItem in scrollNav"
          :key="navItem.label"
          @click.prevent="navItem.scroll"
        >
          {{ navItem.label }}
        </button>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data: () => ({
    isOpen: false,
    isSticky: false,

    scrolled: false,
  }),
  methods: {
    openNav() {
      let body = document.body;
      this.isOpen = !this.isOpen;
      console.log(body);
      this.isOpen
        ? body.classList.add("overflow-hidden")
        : body.classList.remove("overflow-hidden");
    },
  },
  computed: {
    scrollNav() {
      return [
        {
          label: "Home",
          scroll: () => {
            this.openNav();
            const element = document.getElementById("home");
            element.scrollIntoView({ behavior: "smooth" });
          },
        },
        {
          label: "PROJECTS",
          scroll: () => {
            this.openNav();
            const navigationHeight =
              document.querySelector("#navSmall").offsetHeight;
            const element = document.querySelector("#projects");
            const elementTop = element.getBoundingClientRect().top;
            window.scrollTo({
              top: elementTop - navigationHeight,
              behavior: "smooth",
            });
          },
        },
        {
          label: "SKILLS",
          scroll: () => {
            this.openNav();
            const navigationHeight =
              document.querySelector("#navSmall").offsetHeight;
            const element = document.querySelector("#skills");
            const elementTop = element.getBoundingClientRect().top;
            window.scrollTo({
              top: elementTop - navigationHeight,
              behavior: "smooth",
            });
          },
        },
      ];
    },
    scrollLgNav() {
      return [
        {
          label: "HOME",
          scroll: () => {
            const element = document.querySelector("#home");
            const offset = 250;

            element.scrollIntoView({
              behavior: "smooth",
              block: "start",
            });
          },
        },
        {
          label: "PROJECTS",
          scroll: () => {
            const element = document.querySelector("#projects");
            const offset = 100;

            const elementTop = element.getBoundingClientRect().top - offset;

            window.scrollTo({
              top: window.pageYOffset + elementTop,
              behavior: "smooth",
            });
          },
        },
        {
          label: "SKILLS",
          scroll: () => {
            const element = document.querySelector("#skills");
            const offset = 250;

            element.scrollIntoView({
              behavior: "smooth",
              block: "start",
            });
          },
        },
      ];
    },
  },
  mounted() {
    window.addEventListener("scroll", () => {
      if (window.pageYOffset > 0) {
        this.isSticky = true;
      } else {
        this.isSticky = false;
      }
    });
  },
};
</script>

<style scoped>
.custom-shadow {
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000),
    var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
</style>