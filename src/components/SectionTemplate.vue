<template>
  <div>
    <section
      class="section"
      :class="sectionDetails.additionalClasses"
      :id="sectionDetails.id"
    >
      <div class="container grid">
        <h2 class="title has-text-centered">{{ sectionDetails.title }}</h2>
        <h3 class="subtitle has-text-centered">{{ sectionDetails.subtitle }}</h3>
        <slot></slot>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'SectionTemplate',
  props: {
    sectionDetails: Object
  }
}
</script>