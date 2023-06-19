<template>
  <div class="field contact__content">
    <label for="" class="label" :class="config.labelClasses">{{ config.labelName }}</label>
    <textarea name="" id="" class="textarea" :cols="textAreaCols" :rows="textAreaRows" :class="textAreaClasses"></textarea>
  </div>
</template>
<script>
export default {
  name: 'TextAreaComponent',
  props: {
    config: Object
  },
  computed: {
    textAreaRows: function() {
      if (this.config && this.config.elConfig && this.config.elConfig.rows) {
        return this.config.elConfig.rows;
      }
      return 0;
    },
    textAreaCols: function() {
      if (this.config && this.config.elConfig && this.config.elConfig.cols) {
        return this.config.elConfig.cols;
      }
      return 0
    },
    textAreaClasses: function() {
      if (this.config && this.config.elConfig && this.config.elConfig.classes) {
        return this.config.elConfig.classes;
      }
      return "";
    }
  }
}
</script>