<template>
  <div class="qualification__container">
    <QualificationTabs :qualifications="qualifications" @qualificationChange="handleQualificationChange" />
    <div class="qualification__sections">
      <div class="qualification__content">
        <QualificationsData v-for="(milestone, index) in milestones"
          :key="index"
          :milestone="milestone"
          :position="getPosition(index, milestones.length)" />
      </div>
    </div>
  </div>
</template>
<script>
import QualificationTabs from './QualificationTabs.vue';
import QualificationsData from './QualificationsData.vue';

export default {
  name: 'QualificationsContainer',
  props: {
    qualifications: Array
  },
  components: {
    QualificationTabs,
    QualificationsData
  },
  data: function() {
    return {
      activeTab: '#education'
    }
  },
  computed: {
    milestones: function() {
      if (this.activeTab === "#education") {
        return [
            {
              title: "BS in Computer Science",
              subtitle: "UPV Miagao Campus",
              date: "2014-2018"
            },
            {
              title: "High School Graduate",
              subtitle: "RSHS for Region VI",
              date: "2010-2014"
            },
            {
              title: "Elementary Graduate",
              subtitle: "NVC Elementary School",
              date: "2001-2010"
            }
          ];
      }
      return [
        {
          title: "Software Developer",
          subtitle: "DTE Endurance",
          date: "2023-present"
        },
        {
          title: "Junior Copywriter",
          subtitle: "Olly Olly",
          date: "2022-2023"
        },
        {
          title: "Web Developer",
          subtitle: "Eversun",
          date: "2021-2022"
        },
        {
          title: "R&D Engineer",
          subtitle: "Nokia",
          date: "2018-2020"
        },
      ];
    },
  },
  methods: {
    getPosition: function(index, length) {
      let yPos = 'mid';
      let xPos = 'left';
      if (index === 0) {
        yPos = 'start'
      }
      else if ((index + 1) === length) {
        yPos = 'end'
      }

      if (index % 2 !== 0) {
        xPos = 'right';
      }

      return {xPos: xPos, yPos: yPos}
    },
    handleQualificationChange: function(targetTab) {
      this.activeTab = targetTab;
    }
  }
}
</script>