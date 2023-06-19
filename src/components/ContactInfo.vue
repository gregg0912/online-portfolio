<template>
  <div class="contact__information is-flex mb-5">
    <i class="contact__icon is-size-3 mr-3" :class="contactInfo.iconClass"></i>

    <div>
      <h3 class="contact__title has-text-weight-semibold">{{ contactInfo.title }}</h3>
      <span class="contact__subtitle">{{ contactInfo.subtitle }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactInfo',
  props: {
    contactInfo: Object
  }
}
</script>