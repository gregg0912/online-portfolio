<template>
  <header class="header" id="header">
    <nav class="navbar is-fixed-bottom" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a href="#" class="navbar-item has-text-weight-medium">Gregg</a>

        <a
          role="button"
          class="navbar-burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbar__menu"
          @click="navbarBurgerToggle"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      <div class="navbar-menu" id="navbar__menu">
        <div class="navbar-end">
          <a
            v-for="(navigationLink, index) in navigationLinks"
            :key="index"
            :href="navigationLink.href"
            class="navbar-item has-text-weight-medium"
            :class="{ 'is-active': navigationLink.isActive }"
          >
            <i class="nav__icon mr-4" :class="navigationLink.iconClass"></i>
            <span class="nav__text">{{ navigationLink.name }}</span>
          </a>
          <a class="navbar-item has-text-weight-medium" disabled @click="themeToggle">
            <i
              class="uil uil-moon change-theme mr-4"
              id="theme-button"
            ></i>
            <span class="change-theme__text">Change Theme</span>
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'NavigationHeader',
  data: function() {
    return {
      navigationLinks: [
        {name: "Home", href: "#home", iconClass: "uil uil-estate", isActive: true},
        {name: "About", href: "#about", iconClass: "uil uil-user", isActive: false},
        {name: "Skills", href: "#skills", iconClass: "uil uil-file-info-alt", isActive: false},
        {name: "Qualification", href: "#qualification", iconClass:"uil uil-award", isActive: false},
        {name: "Portfolio", href: "#portfolio", iconClass: "uil uil-image", isActive: false},
        {name: "Contact", href: "#contact", iconClass: "uil uil-message", isActive: false},
      ],
    };
  },
  methods: {
    navbarBurgerToggle: function(e) {
      const clickedButton = e && e.target;
      const target = clickedButton.dataset && clickedButton.dataset.target;
      const $target = document.getElementById(target);
      if (clickedButton && clickedButton.classList) {
        clickedButton.classList.toggle('is-active');
      }

      if ($target && $target.classList) {
        $target.classList.toggle('is-active');
      }
    },
    getCurrentTheme: function () {
      if (document && document.body && document.body.classList)
      {
        return document.body.classList.contains("dark-theme") ? "dark" : "light";
      }
    },
    getCurrentIcon: function () {
      const themeButton = document.getElementById("theme-button");
      if (themeButton && themeButton.classList) {
        return themeButton.classList.contains("uil-sun") ? "uil-moon" : "uil-sun";
      }
    },
    themeToggle: function() {
      const themeButton = document.getElementById("theme-button");

      if (document && document.body && document.body.classList) {
        document.body.classList.toggle("dark-theme");
        themeButton.classList.toggle("uil-sun");

        localStorage.setItem("selected-theme", this.getCurrentTheme());
        localStorage.setItem("selected-icon", this.getCurrentIcon());
      }
    }
  }
}
</script>