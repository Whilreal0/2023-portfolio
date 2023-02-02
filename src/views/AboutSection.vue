<template>
  <section id="skills" class="py-10  px-2.5 md:px-0 mt-10 relative ">
    <h3 id="header" class="mb-10 text-center text-2xl font-semibold">Knowledge and Skills</h3>
    <div class="flex flex-col items-center justify-center w-full mb-10">
      <div class="w-full max-w-[300px] sm:max-w-[400px] md:max-w-full">
        <div
          class="
            grid grid-cols-2
            sm:grid-cols-3
            md:grid-cols-4
            lg:grid-cols-5
            gap-5
          "
        >
          <div
            class="h-36 max-h-[135px] shadow-lg rounded-md hover:translate-y-[-12px] hover:translate-x-1 transition-all duration-300"
            v-for="(item, index) in skills"
            :key="index"
          >
            <div
              class="
                flex
                items-center
                justify-center
                w-full
                h-[70%]
                max-h-[80%]
                
              "
            >
              <i class="text-7xl" :class="item.icon"></i>
            </div>
            <div class="max-h-[30%] text-center">
              <h2>{{ item.name }}</h2>
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
    skills: [
      {
        name: "HTML5",
        icon: "devicon-html5-plain colored",
        type: "logo",
      },
      {
        name: "Javascript",
        icon: "devicon-javascript-plain colored",
        type: "logo",
      },
      {
        name: "CSS3",
        icon: "devicon-css3-plain colored",
        type: "logo",
      },
      {
        name: "Tailwind Css",
        icon: "devicon-tailwindcss-plain colored",
        type: "logo",
      },
      {
        name: "Vue.js",
        icon: "devicon-vuejs-plain colored",
        type: "logo",
      },
      {
        name: "Vuetify",
        icon: "devicon-vuetify-line colored",
        type: "logo",
      },
      {
        name: "Git",
        icon: "devicon-git-plain colored",
        type: "logo",
      },
      {
        name: "Github",
        icon: "devicon-github-original colored",
        type: "logo",
      },

      {
        name: "Wordpress",
        icon: "devicon-wordpress-plain colored",
        type: "logo",
      },
      {
        name: "Bootstrap",
        icon: "devicon-bootstrap-plain colored",
        type: "logo",
      },
      {
        name: "Adobe XD",
        icon: "devicon-xd-plain colored",
        type: "logo",
      },
      {
        name: "Figma",
        icon: "devicon-figma-plain colored",
        type: "logo",
      },
      {
        name: "Photoshop",
        icon: "devicon-photoshop-plain colored",
        type: "logo",
      },
      {
        name: "Canva",
        icon: "devicon-canva-original colored",
        type: "logo",
      },
    ],
    cssCize: "90px",
  }),
};
</script>

<style>
</style>