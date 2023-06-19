<template>
  <div class="contact__container container grid">
    <div class="columns">
      <div class="column is-12-mobile is-6-tablet">
        <ContactInfo v-for="(contactInfo, index) in contactInformation"
          :key="index"
          :contact-info="contactInfo"
        />
      </div>
      <div class="column is-12-mobile is-6-tablet">
        <form action="" class="contact__form grid">
          <div class="contact__inputs columns">
            <div class="column is-12-mobile is-6-tablet">
              <InputText :config="nameConfig" />
            </div>
            <div class="column is-12-mobile is-6-tablet">
              <InputText :config="emailConfig" />
            </div>
          </div>
          <InputText :config="projectConfig" />
          <TextAreaComponent :config="textAreaConfig" />
          <div class="field">
            <div class="control">
              <a href="#" class="button button--flex">
                Send Message
                <i class="uil uil-message button__icon is-size-5 ml-2"></i>
              </a>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
import ContactInfo from './ContactInfo.vue';
import InputText from './InputText.vue';
import TextAreaComponent from './TextAreaComponent.vue';

export default {
  name: 'ContactContainer',
  components: {
    ContactInfo,
    InputText,
    TextAreaComponent
  },
  props: {
    contactInformation: Array
  },
  data: function() {
    return {
      nameConfig: {
        labelName: "Name",
        labelClasses: "contact__label"
      },
      emailConfig: {
        labelName: "Email",
        labelClasses: "contact__label"
      },
      projectConfig: {
        labelName: "Project",
        labelClasses: "contact__label"
      },
      textAreaConfig: {
        labelName: "Message",
        labelClasses: "contact__label",
        elConfig: {
          cols: 0,
          rows: 7,
          classes: "contact__input"
        }
      }
    }
  }
}
</script>