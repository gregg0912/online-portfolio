<template>
<div class="qualification__data">
  <div
    v-if="position.xPos === 'right'"
    key="extraDiv"
  ></div>

  <div
    v-if="position.xPos === 'right'"
    key="rounderLineDiv"
  >
    <span class="qualification__rounder"></span>
    <span
      v-if="position.yPos === 'mid'" class="qualification__line"
      key="lineDiv"
    ></span>
  </div>

  <div :class="{'has-text-right': position.xPos === 'right'}">
    <h3 class="qualification__title is-size-5">{{ milestone.title }}</h3>
    <span class="qualification__subtitle is-size-6">{{ milestone.subtitle }}</span>
    <div class="qualification__calendar is-size-7">
      <i class="uil uil-calendar-alt">{{ milestone.date }}</i>
    </div>
  </div>

  <div
    v-if="position.xPos === 'left'"
    key="rounderLineDiv">
    <span class="qualification__rounder"></span>
    <span
      v-if="position.yPos !== 'end'"
      key="lineDiv"
      class="qualification__line"></span>
  </div>
</div>
</template>

<script>
export default {
  name: 'QualificationsData',
  props: {
    milestone: Object,
    position: Object
  }
}
</script>