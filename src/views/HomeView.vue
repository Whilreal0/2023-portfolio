<template>
  <main class="  ">
    <div class="max-w-[61rem] mx-auto px-3 md:px-5 ">
      <HomeSection />
      <ProjectSection />
      <AboutSection />
    </div>
  </main>
</template>

<script>
import HomeSection from "@/views/HomeSection";
import ProjectSection from "@/views/ProjectSection";
import AboutSection from "@/views/AboutSection";
export default {
  components: {
    HomeSection,ProjectSection,AboutSection
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&display=swap');


body{
  font-family: 'Space Grotesk', sans-serif;
  background: #ECF9FF;
  
}
</style>