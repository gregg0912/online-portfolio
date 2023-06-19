<template>
  <div id="app">
    <NavigationHeader />
    <MainBody />
    <FooterComponent />
    <ScrollTop />
  </div>
</template>

<script>
import NavigationHeader from "./components/NavigationHeader.vue";
import MainBody from "./components/MainBody.vue";
import FooterComponent from "./components/FooterComponent.vue"
import ScrollTop from "./components/ScrollTop.vue";

export default {
  name: 'App',
  components: {
    NavigationHeader,
    MainBody,
    FooterComponent,
    ScrollTop
  },
  methods: {
    scrollActive: function() {
      const sections = document.querySelectorAll("section[id]");
      const scrollY = window.pageYOffset;
      sections.forEach((current) => {
        const sectionHeight = current.offsetHeight;
        const sectionTop = current.offsetTop - 100;
        let sectionId = current.getAttribute("id");

        if (document.querySelector(`.navbar-item[href*=${sectionId}]`))
        {
          if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
            document
              .querySelector(`.navbar-item[href*=${sectionId}]`)
              .classList.add("is-active");
          } else {
            document
              .querySelector(`.navbar-item[href*=${sectionId}]`)
              .classList.remove("is-active");
          }
        }
      });
    },
    scrollHeader: function() {
      const nav = document.getElementById("header");
      if (nav) {
        if (window.scrollY >= 80) {
          nav.classList.add("scroll-header");
        } else {
          nav.classList.remove("scroll-header");
        }
      }
    },
    scrollUp: function () {
      const scrollUp = document.getElementById("scroll-up");

      if (scrollUp && scrollUp.classList) {
        if (window.scrollY >= 560) {
          scrollUp.classList.add("show-scroll");
        } else {
          scrollUp.classList.remove("show-scroll");
        }
      }
    }
  },
  mounted: function () {
    window.addEventListener("scroll", this.scrollActive);
    window.addEventListener("scroll", this.scrollHeader);
    window.addEventListener("scroll", this.scrollUp);

    if (this.selectedTheme && document.body && document.body.classList) {
      document.body.classList[this.selectedTheme === "dark" ? "add" : "remove"](
        "dark-theme"
      );
    }
  },
  data: function() {
    return {
      selectedTheme: localStorage.getItem("selected-theme"),
      selectedIcon: localStorage.getItem("selected-icon")
    }
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
