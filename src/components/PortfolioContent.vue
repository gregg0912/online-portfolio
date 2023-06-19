<template>
  <div class="portfolio__content mb-3">
    <div class="portfolio__box box has-text-centered">
      <img :src="portfolioDetail.img" alt="" class="portfolio__img">
      <div class="portfolio__data">
        <h3 class="portfolio__title is-size-5 has-text-weight-semibold mb-3">{{ portfolioDetail.title }}</h3>
        <p class="portfolio__description mb-3">{{ portfolioDetail.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PortfolioContent',
  props: {
    portfolioDetail: Object
  }
}
</script>