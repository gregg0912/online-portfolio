<template>
  <footer class="footer">
    <div class="content">
      <div class="footer__container container grid">
        <div>
          <h1 class="footer__title is-size-4 mb-1 has-text-weight-semibold">Gregg</h1>
          <span class="footer__subtitle">Software Developer</span>
        </div>

        <div class="footer__socials">
          <a
            v-for="(socialLink, index) in socialLinks"
            :key="index"
            :href="socialLink.href"
            target="_blank"
            class="footer__social mr-5 has-text-white"
          >
            <i :class="socialLink.iconClass"></i>
          </a>
        </div>
      </div>

      <p class="has-text-centered footer__copy">&#169; Gregg Marionn Icay</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponent',
  data: function() {
    return {
      socialLinks: [
        {href: "https://www.facebook.com/greggmarionn.icay/", iconClass: "uil uil-facebook-f"},
        {href: "https://twitter.com/noGREGGrets", iconClass: "uil uil-twitter-alt"},
        {href: "https://discordapp.com/users/9183", iconClass: "uil uil-discord"},
      ]
    }
  }
}
</script>