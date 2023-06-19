<template>
  <!--==================== PORTFOLIO ====================-->
  <div>
    <SectionTemplate :section-details="sectionDetails">
      <PortfolioContainer :portfolio-details="portfolioDetails" />
    </SectionTemplate>
  </div>
</template>
<script>
import SectionTemplate from './SectionTemplate.vue';
import PortfolioContainer from './PortfolioContainer.vue';

export default {
  name: 'PortfolioSection',
  components: {
    SectionTemplate,
    PortfolioContainer
  },
  data: function() {
    return {
      portfolioDetails: [
        {
          title: "PAGOD",
          description: "Web-based software application that will serve as a pre-enlistment guide for students of the University of the Philippines.",
          img: "assets/img/portfolio1.png"
        },
        {
          title: "Org_Y",
          description: "Web-based software application made for the various organizations of University of the Philippines Visayas.",
          img: "assets/img/portfolio2.png"
        },
        {
          title: "GitHelp",
          description: "Web platform made to be a place for registered teachers to put their lessons online and for students with accounts to read them.",
          img: "assets/img/portfolio3.png"
        },
        {
          title: "DorME",
          description: "Web-based software application for students, incoming or returning, to view housing establishments which are not part of the lodging services that UPV provides.",
          img: "assets/img/portfolio4.png"
        },
      ],
      sectionDetails: {
        additionalClasses: "portfolio",
        title: "Portfolio",
        subtitle: "What I've worked on",
        id: "portfolio"
      }
    }
  }
}
</script>