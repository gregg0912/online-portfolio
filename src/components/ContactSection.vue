<template>
  <SectionTemplate :section-details="sectionDetails">
    <ContactContainer :contact-information="contactInformation" />
  </SectionTemplate>
</template>
<script>
import ContactContainer from './ContactContainer.vue';
import SectionTemplate from './SectionTemplate.vue';

export default {
  name: 'ContactSection',
  components: {
    SectionTemplate,
    ContactContainer
  },
  data: function() {
    return {
      contactInformation: [
        { title: "Phone", subtitle: "(+63)908 199 0388", iconClass: "uil uil-phone-alt" },
        { title: "Email", subtitle: "gregg.icay@dteendurance.com", iconClass: "uil uil-envelope" },
        { title: "Location", subtitle: "Villa Atong-Atang, C. Laserna, Kalibo, Aklan", iconClass: "uil uil-map-marker" }
      ],
      sectionDetails: {
        additionalClasses: "contact is-full-height-desktop",
        title: "Contact",
        subtitle: "Request a project",
        id: "contact"
      }
    }
  }
}
</script>