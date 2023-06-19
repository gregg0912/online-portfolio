<template>
  <div class="portfolio__container container">
    <div>
      <PortfolioContent
        v-for="(portfolioDetail, index) in portfolioDetails"
        :key="index"
        :portfolio-detail="portfolioDetail"
      />
    </div>
  </div>
</template>
<script>
import PortfolioContent from './PortfolioContent.vue';

export default {
  name: 'PortfolioContainer',
  components: {
    PortfolioContent
  },
  props: {
    portfolioDetails: Array
  }
}
</script>