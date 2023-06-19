<template>
  <!--==================== SKILLS ====================-->
  <div>
    <SectionTemplate :section-details="sectionDetails">
      <SkillsContainer :skill-details="skillDetails" />
    </SectionTemplate>
  </div>
</template>

<script>
import SectionTemplate from './SectionTemplate.vue';
import SkillsContainer from './SkillsContainer.vue';

export default {
  name: 'SkillsSection',
  components: {
    SkillsContainer,
    SectionTemplate
  },
  data: function() {
    return {
      skillDetails: [
        {
          position: "Copywriter",
          duration: "Less than a year",
          iconClass: "uil uil-file-plus-alt",
          skills: [
            {name: "Google Suite", rating: "100"},
            {name: "ChatGPT", rating: "100"},
            {name: "CopyAI", rating: "100"},
            {name: "Wordpress", rating: "80"},
          ],
          isOpen: true
        },
        {
          position: "Web Developer",
          duration: "More than 1 year",
          iconClass: "uil uil-brackets-curly",
          skills: [
            {name: "HTML", rating: "95"},
            {name: "CSS3", rating: "70"},
            {name: "JavaScript", rating: "85"},
            {name: "JQuery", rating: "85"},
            {name: "PHP", rating: "95"},
            {name: "Laravel", rating: "85"},
          ],
          isOpen: false
        },
        {
          position: "R&D Engineer",
          duration: "More than 2 years",
          iconClass: "uil uil-keyboard-alt",
          skills: [
            {name: "C++", rating: "70"},
            {name: "Python3", rating: "80"},
            {name: "K3", rating: "70"},
          ],
          isOpen: false
        },
      ],
      sectionDetails: {
        additionalClasses: "skills is-full-height-desktop",
        title: "Skills",
        subtitle: "What I know",
        id: "skills"
      }
    }
  },
}
</script>