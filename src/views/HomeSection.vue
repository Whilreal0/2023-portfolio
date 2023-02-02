<template>
  <section
    id="home"
    class="
      w-full
      min-w-full min-h-screen
      flex
      items-center
      justify-center
      px-2.5
      md:px-0
    "
  >
    <div class="-mt-16 md:-mt-20">
      <div class="flex flex-col gap-2">
        <h2 class="text-3xl sm:text-5xl md:text-6xl">
          <strong>Hi, Im Whilmer Realigue </strong>
         
        </h2>
        <p class="text-lg sm:text-2xl md:text-[2rem]">
          A front-end Web Developer with a passion for crafting beautiful and
          responsive interfaces and Web Applications.
        </p>
        <div>
          <span class="flex flex-row items-center gap-2 mt-10">
            <button class="text-xl">
              <a
                href="https://www.linkedin.com/in/whilmer-realigue-a6093b229"
                target="_blank"
              >
                <i class="devicon-linkedin-plain colored"></i>
              </a>
            </button>
          </span>
          <div class="mt-10">
            <button
              class="
                flex
                text-sm
                gap-2
                justify-center
                items-center
                text-[#FFFBEB]
                bg-[#66ceff]
                hover:bg-[#FFFBEB] hover:fill-[#66ceff] hover:text-[#66ceff]
                fill-[#FFFBEB]
                px-3
                py-1.5
                rounded-md
                uppercase
              "
              @click="openResume"
            >
              Resume
              <box-icon class="" size="sm" name="link-external"></box-icon>
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    async openResume() {
      const response = await fetch("/whilmer-resume-2023.pdf");
      const file = await response.blob();
      const fileURL = URL.createObjectURL(file);
      window.open(fileURL, "_blank");
      console.log(response);
    },
  },
};
</script>

<style>
</style>