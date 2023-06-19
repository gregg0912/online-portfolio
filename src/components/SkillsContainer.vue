<template>
  <div class="skills__container grid">
    <SkillsContent
      v-for="(skillDetail, index) in skillDetails"
      :key="index"
      :skill-detail="skillDetail"
    />
  </div>
</template>
<script>
import SkillsContent from './SkillsContent.vue';

export default {
  name: 'SkillsContainer',
  components: {
    SkillsContent
  },
  props: {
    skillDetails: Array
  }
}
</script>