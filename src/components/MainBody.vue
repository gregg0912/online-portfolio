<template>
  <main class="main">
    <HomeSection />
    <AboutSection />
    <SkillsSection />
    <QualificationsSection />
    <PortfolioSection />
    <ContactSection />
  </main>
</template>

<script>
import AboutSection from './AboutSection.vue';
import HomeSection from './HomeSection.vue';
import SkillsSection from './SkillsSection.vue';
import QualificationsSection from "./QualificationsSection.vue";
import PortfolioSection from './PortfolioSection.vue';
import ContactSection from './ContactSection.vue';
export default {
  name: 'MainBody',
  components: {
    HomeSection,
    AboutSection,
    SkillsSection,
    QualificationsSection,
    PortfolioSection,
    ContactSection
  }
}
</script>