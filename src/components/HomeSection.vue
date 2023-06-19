<template>
  <!--==================== HOME ====================-->
  <section class="home section is-full-height-desktop" id="home">
    <div class="home__container container grid">
      <HomeContent />
      <HomeScroll />
    </div>
  </section>
</template>
<script>
import HomeContent from './HomeContent.vue';
import HomeScroll from './HomeScroll.vue';

export default {
  name: 'HomeSection',
  components: {
    HomeContent,
    HomeScroll
  }
}
</script>