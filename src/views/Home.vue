<template>
  <div class="home">
    <div class="links">
      <HomeLink id="position-calculator" label="Position Calculator" description="See how good your players could be at any position!" img-src="/img/banner-position-calculator.svg"/>
      <HomeLink id="batter-projections" label="Batter Projections" description="Project full-season stats from batter ratings!" img-src="/img/banner-pitcher-projections.svg"/>
      <HomeLink id="pitcher-projections" label="Pitcher Projections" description="Project full-season stats from pitcher ratings!" img-src="/img/banner-batter-projections.svg"/>
      <HomeLink id="about" label="About" description="Learn more about the OOTP Calculator!" img-src="/img/banner-about.svg"/>
    </div>
  </div>
</template>

<script>
import HomeLink from '../components/HomeLink.vue';

export default {
  name: 'Home',
  components: { HomeLink },
  data() {
    return {
      images: []
    }
  },
  created() {
    document.title = 'OOTP Calculator';
  },
  mounted() {
    // Pre-load hover images
    let urls = ['/img/banner-batter-projections-hover.svg', '/img/banner-position-calculator-hover.svg',
    '/img/banner-pitcher-projections-hover.svg', '/img/banner-about-hover.svg'];
    for (let url of urls) {
      let img = new Image();
      img.src = url;
      this.images.push(img);
    }
  }
}
</script>

<style scoped>
.links {
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>