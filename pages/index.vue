<template>
  <div class="main--outer-wrapper">
    <div class="main--scroll">
      <ScrollElement :headers="headers" />
    </div>

    <div class="main--introduction">
      <BlackHoleBackground scrollTo="#About" />
    </div>

    <!-- SKILLS SECTION -->
    <div
      class="main--about"
      data-aos="fade-up"
      data-aos-easing="ease"
      data-aos-duration="1200"
    >
      <lazy-about-section id="About" scrollTo="#Skills" />
    </div>

    <!-- SKILLS SECTION -->
    <div
      class="main--skills"
      data-aos="fade-up"
      data-aos-easing="ease"
      data-aos-duration="1200"
    >
      <lazy-skills-section id="Skills" scrollTo="#Timeline" />
    </div>

    <!-- TIMELINE SECTION -->
    <div
      class="main--timeline"
      data-aos="fade-up"
      data-aos-easing="ease"
      data-aos-duration="1200"
    >
      <lazy-timeline-block id="Timeline" />
    </div>

    <div
      class="main--contact"
      data-aos="fade-up"
      data-aos-easing="ease"
      data-aos-duration="1200"
    >
      <lazy-contact-section id="Contact" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        { name: "About Me", id: "#About" },
        { name: "Skills", id: "#Skills" },
        { name: "Experience", id: "#Timeline" },
        { name: "Contact", id: "#Contact" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@keyframes fadeIn-down-arrow {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes fadeIn-scroll {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.main--down-arrow {
  animation: fadeIn-down-arrow 3s;
}

.main--scroll {
  animation: fadeIn-scroll 2s;
}

.main--outer-wrapper {
  background: #002142;
}

.main--about {
  animation: fadeIn-about 2s;
}
</style>