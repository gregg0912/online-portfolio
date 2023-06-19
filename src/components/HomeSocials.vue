<template>
  <div class="home__social">
    <a
      v-for="(socialLink, index) in socialLinks"
      :key="index"
      :href="socialLink.href"
      target="_blank"
      class="home__social-icon is-size-3-desktop is-size-5-touch"
    >
      <i :class="socialLink.iconClass"></i>
    </a>
  </div>
</template>
<script>
export default {
  name: 'HomeSocials',
  data: function() {
    return {
      socialLinks: [
        { href: "https://www.linkedin.com/in/gregg-marionn-icay-7a6701155/", iconClass: "uil uil-linkedin-alt" },
        { href: "https://gitlab.com/greggicay", iconClass: "uil uil-gitlab" },
        { href: "https://github.com/gregg0912", iconClass: "uil uil-github-alt" },
      ]
    }
  }
}
</script>