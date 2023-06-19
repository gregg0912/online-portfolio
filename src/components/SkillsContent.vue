<template>
  <div class="skills__content"
    :class="{ 'skills__open' : skillDetail.isOpen, 'skills__close' : !skillDetail.isOpen }">
    <div class="skills__header is-flex is-align-items-center mb-6" @click="toggleSkills">
      <i class="skills__icon is-size-3 mr-3" :class="skillDetail.iconClass"></i>

      <div>
        <h1 class="skills__title">{{ skillDetail.position }}</h1>
        <span class="skills__subtitle">{{ skillDetail.duration }}</span>
      </div>

      <i class="uil uil-angle-down skills__arrow ml-auto is-size-3"></i>
    </div>

    <div class="skills__list grid">
      <div
        class="skills__data"
        v-for="(skill, index) in skillDetail.skills"
        :key="index"
      >
        <div class="skills__title is-flex is-justify-content-space-between">
          <h3 class="skills__name">{{ skill.name }}</h3>
          <span class="skills__number">{{ skill.rating }} %</span>
        </div>
        <progress class="progress is-small" :value="skill.rating" max="100"></progress>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'SkillsContent',
  props: {
    skillDetail: Object
  },
  data: function() {
    return {}
  },
  methods: {
    toggleSkills() {
      const skillsContent = document.querySelectorAll(".skills__content");
      const itemClass = this.$el && this.$el.className;

      skillsContent.forEach((content) => {
        content.className = "skills__content skills__close";
      });
      if (itemClass === "skills__content skills__close") {
        this.$el.className = "skills__content skills__open";
      }
    }
  }
}
</script>