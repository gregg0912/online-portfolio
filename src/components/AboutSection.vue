<template>
  <!--==================== ABOUT ====================-->
  <SectionTemplate :section-details="sectionDetails">
    <AboutContainer />
  </SectionTemplate>
</template>
<script>
import SectionTemplate from './SectionTemplate.vue';
import AboutContainer from './AboutContainer.vue'

export default {
  name: 'AboutSection',
  components: {
    SectionTemplate,
    AboutContainer
  },
  data: function() {
    return {
      sectionDetails: {
        additionalClasses: "about is-full-height-desktop",
        title: "About",
        subtitle: "Get to know me",
        id: "about"
      }
    }
  }
}
</script>