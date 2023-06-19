<template>
  <div class="home__content grid">
    <HomeSocials />
    <HomeImage />
    <HomeData />
  </div>
</template>
<script>
import HomeData from './HomeData.vue';
import HomeImage from './HomeImage.vue';
import HomeSocials from './HomeSocials.vue';

export default {
  name: 'HomeContent',
  components: {
    HomeImage,
    HomeData,
    HomeSocials
  }
}
</script>