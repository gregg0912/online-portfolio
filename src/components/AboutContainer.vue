<template>
  <div class="about__container columns is-mobile is-multiline is-vcentered">
    <div class="column is-12-mobile is-12-tablet is-6-desktop is-flex is-justify-content-space-evenly">
      <img src="assets/img/computer-typing.gif" alt="" class="about__img">
    </div>

    <div class="about__data column is-12-mobile is-12-tablet is-6-desktop">
      <p class="about__description mb-6">A software engineer with experience in the telecommunication industry and web development. With high skills in writing code in PHP, and JavaScript through maintenance tasks and test creation.</p>
      <div class="about__info level is-mobile mb-6">
        <div
          class="level-item has-text-centered"
          v-for="(aboutDetail, index) in aboutDetails"
          :key="index"
        >
          <div>
            <p class="title">{{ aboutDetail.title }}</p>
            <p class="heading" v-html="aboutDetail.name"></p>
          </div>
        </div>
      </div>

      <div class="about__buttons">
        <a download="" href="assets/cv/gregg-icay-cv.docx" class="button is-medium">
          <span class="is-size-6">Download Resume</span>
          <i class="uil uil-download-alt button__icon is-size-5 ml-2"></i>
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'AboutContainer',
  data: function() {
    return {
      aboutDetails: [
        {title: "04+", name: "Years <br /> experience"},
        {title: "10+", name: "Completed <br /> projects"},
        {title: "4", name: "Companies <br /> worked"},
      ],
    }
  }
}
</script>
