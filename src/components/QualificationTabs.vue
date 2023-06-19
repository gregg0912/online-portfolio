<template>
  <div class="qualification__tabs tabs is-centered">
    <ul>
      <li
        v-for="(qualification, index) in qualifications"
        :key="index"
        class="qualification__button"
        :class="{'is-active': qualification.isActive}"
        :data-target="qualification.target"
        @click="pickTab">
        <a>
          <span class="icon">
            <i
              :class="qualification.iconClass"
              aria-hidden="true"
            ></i>
          </span>
          <span>{{ qualification.name }}</span>
        </a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'QualificationTabs',
  props: {
    qualifications: Array
  },
  methods: {
    pickTab: function(e) {
      const closestLi = e && e.target && e.target.closest('li');
      const targetName = closestLi.dataset && closestLi.dataset.target;
      const tabs = document.querySelectorAll(".qualification__button");

      tabs.forEach((tab) => {
        if (tab && tab.classList) {
          tab.classList.remove("is-active");
        }
      });

      if (closestLi && closestLi.classList) {
        closestLi.classList.add("is-active");
      }

      this.$emit("qualificationChange", targetName);
    }
  }
}
</script>