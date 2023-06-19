<template>
  <!--==================== QUALIFICATION ====================-->
  <div>
    <SectionTemplate :section-details="sectionDetails">
      <QualificationsContainer :qualifications="qualifications"></QualificationsContainer>
    </SectionTemplate>
  </div>
</template>
<script>
import QualificationsContainer from './QualificationsContainer.vue';
import SectionTemplate from './SectionTemplate.vue';

export default {
  name: "QualificationsSection",
  components: {
    QualificationsContainer,
    SectionTemplate
  },
  data: function() {
    return {
      qualifications: [
        {
          name: "Education",
          isActive: true,
          target: "#education",
          iconClass: "uil uil-graduation-cap",
          id: "education"
        },
        {
          name: "Work",
          isActive: false,
          target: "#work",
          iconClass: "uil uil-briefcase-alt",
          id: "work"
        }
      ],
      sectionDetails: {
        additionalClasses: "qualification is-full-height-desktop",
        title: "Qualification",
        subtitle: "My Personal Journey",
        id: "qualification"
      }
    }
  }
}
</script>