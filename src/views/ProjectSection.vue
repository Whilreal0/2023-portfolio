<template>
  <section id="projects" class="px-2.5  md:px-0 relative">
    <h3 id="header" class="mb-10 text-center text-2xl font-semibold">Projects</h3>
    <div class="flex flex-col gap-8">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-5 items-center ">
        <div
          class="shadow-md rounded-md h-[18rem] max-w-[540px] w-full max-h-[18rem] mx-auto"
          v-for="(item, index) in items"
          :key="index"
        >
          <div class="h-[75%] rounded-md">
            <img
              v-if="!item.showOverlay"
              :src="item.img"
              alt=""
              class="
                object-cover
                bg-center
                h-full
                w-full
                max-w-full
                rounded-t-md
                brightness-75
              "
            />

            <div
              v-if="item.showOverlay"
              class="
                h-full
                w-full
                rounded-t-md
                transition-all
                duration-1000
                ease-in
                transform
                p-2.5
                flex
                items-center
                justify-center 
                bg-[#FFFBEB]
              "
            >
              {{ item.description }}
            </div>
          </div>
          <hr />

          <div class="h-[25%] px-2.5 flex flex-col justify-center bg-white rounded-b-md">
            <div class="flex flex-row items-center justify-between">
              <span class="text-xl font-semibold flex items-center">
                <a :href="item.link"  target="_blank">
                  {{ item.title }}
                  <box-icon :size="linkIcon" name="link"></box-icon>
                </a>
              </span>
              <button
                @click="toggleOverlay(index)"
                class="
                  text-red-600
                  rounded-md
                  text-sm
                  py-1
                  px-2.5
                  hover:bg-none
                "
              >
                More Info
              </button>
            </div>
            <div class=" font-bold flex flex-row items-center gap-2">
              <small class="text-black/60">{{ item.stack[0] }}</small>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data: () => ({
    linkIcon: ".9rem",
    items: [
      {
        title: "Shutter Dream",
        link: "https://photography-site-bal.pages.dev/",
        stack: ["Vue.js, TailwindCSS "],
        description:
          "Capturing Life's Treasured Moments with Artistic Precision.",
        img: [require("@/assets/Images/ShutterDream.jpg")],
        showOverlay: false,
      },
      {
        title: "Castra Gears",
        link: "https://dev-castra-gears.pantheonsite.io/",
        stack: ["Wordpress"],
        description:
          "Unleash Your Adventure Spirit with Our Premium Outdoors Gear.",
        img: [require("@/assets/Images/CastraGear.jpg")],
        showOverlay: false,
      },
      {
        title: "Simple To Do List",
        link: "https://todoapp-bywhil.netlify.app/",
        stack: ["Vue.js, Vuetify"],
        description: "Manage tasks easily with simple CRUD to-do list app.",
        img: [require("@/assets/Images/Todolist.jpg")],
        showOverlay: false,
      },
      {
        title: "Vigilatte Coffee House",
        link: "https://49d674ae.coffee-4rk.pages.dev/",
        stack: ["Vue.js, TailwindCSS"],
        description: "Experience the taste of handcrafted coffee and baked goods at Vigilante Coffee House, a place for community",
        img: [require("@/assets/Images/Coffee.jpg")],
        showOverlay: false,
      },
      {
        title: "PH Covid Tracker",
        link: "https://whilmer-c-19-tracker-app.netlify.app/",
        stack: ["Vue.js, TailwindCSS, API"],
        description: "A simple Covid Tracker Using API",
        img: [require("@/assets/Images/Covid-tracker.jpg")],
        showOverlay: false,
      },
      {
        title: "Weather App",
        link: "https://mer-weather-app.netlify.app/",
        stack: ["Vue.js, TailwindCSS, GetWeather Api"],
        description: "Reliable and up-to-date weather information with a simple interface.",
        img: [require("@/assets/Images/Weather.jpg")],
        showOverlay: false,
      },
     


    ],
    hover: false,
  }),
  methods: {
    toggleOverlay(index) {
      this.items[index].showOverlay = !this.items[index].showOverlay;
    },
  },
};
</script>

<style>
.slide-down-enter {
  transform: translateY(-100%);
}
.slide-down-enter-active {
  transform: translateY(0);
  transition: transform 0.5s;
}
.slide-down-leave-active {
  transform: translateY(-100%);
  transition: transform 0.5s;
}
</style>