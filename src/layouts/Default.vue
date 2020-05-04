<template>
  <div id="app">

    <header class="header">
      <div class="header__left">
        <Logo v-if="showLogo" />
      </div>

      <nav class="nav">
            <g-link class="nav__link" to="/">Home</g-link>
            <g-link class="nav__link" to="/about/">About</g-link>
            <g-link class="nav__link text-green text base" to="/blog/">blog</g-link>
            <g-link class="nav__link" to="/portfolio/">Portfolio</g-link>
            <g-link class="nav__link" to="/contact/">Contact</g-link>
      </nav>

      <div class="header__right">
        <ToggleTheme />
      </div>
    </header>

    <main class="main">
      <slot/>
    </main>

    <footer class="footer">
        <span class="footer__copyright">Copyright © {{ new Date().getFullYear() }}. </span>
      <span class="footer__links">Made with ❤️ by <a href="//www.uelsmall.netlify.app"> U'el Small</a></span>
      
    </footer>
<!-- 
    <footer class="footer">
      <div class="social-media-links">
          <a href="https://dev.to/uelSmall" target="_blank" rel="noopener">Dev</a>
          <a href="https://instagram.com/uelSmall" target="_blank" rel="noopener">Instagram</a>
          <a href="https://twitter/Azdrian" target="_blank" rel="noopener">Twitter</a>
          <a href="https://github.com/uelSmall" target="_blank" rel="noopener">GitHub</a>
          <a href="https://linkedin.com/uelSmall" target="_blank" rel="noopener">LinkedIn</a>
          <a href="https://freecodecamp.org/uelSmall" target="_blank" rel="noopener">Freecodecamp</a>
      </div>
      <div class="footer-info">
        <span class="footer__copyright">Copyright © {{ new Date().getFullYear() }}. </span>
      <span class="footer__links">Made with ❤️ by <a href="//www.uelsmall.netlify.app"> U'el Small</a></span>
      </div>
    </footer> -->
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import ToggleTheme from '~/components/ToggleTheme.vue'

export default {
  props: {
    showLogo: { default: true }
  },
  components: {
    Logo,
    ToggleTheme
  }
}
</script>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  min-height: var(--header-height);
  padding: 0 calc(var(--space) / 2);
  top:0;
  z-index: 10;

  &__left,
  &__right {
    display: flex;
    align-items: center;
  }
.nav__link {
  margin-left: 20px;
}
  @media screen and (min-width: 1300px) {
    //Make header sticky for large screens
    position: sticky;
    width: 100%;
  }
}

.main {
  margin: 0 auto;
  padding: 1.5vw 15px 0;
}

.footer {
  
  display: flex;
  align-items: center;
  justify-content: center;
  padding: calc(var(--space) / 2);
  text-align: center;
  font-size: .8em;

  > span {
    margin: 0 .35em;
  }

  a {
    color: currentColor;
  }
}
.social-media-links a {
  margin-right: 1rem;
}
</style>
