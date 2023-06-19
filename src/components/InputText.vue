<template>
  <div class="field contact__content">
    <label for="" class="label" :class="config.labelClasses">{{ config.labelName }}</label>
    <div class="control">
      <input type="text" class="input" />
    </div>
  </div>
</template>
<script>
export default {
  name: 'InputText',
  props: {
    config: Object
  }
}
</script>