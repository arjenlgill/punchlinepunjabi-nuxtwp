<template>
  <div>
     <div class="burger-menu-popup">
      <div class="burger-menu-exit-button">X</div>

      <div class="burger-menu-nav-link-container">
        <a class="burger-menu-nav-link hover" href="features.html"
          >Features</a
        >
        <a class="burger-menu-nav-link hover" href="playlists.html"
          >Playlists</a
        >
        <a class="burger-menu-nav-link hover" href="dictionary.html"
          >Dictionary</a
        >
        <a class="burger-menu-nav-link hover" href="about.html">About</a>
      </div>
    </div>
      <!--slide-down nav bar-->

      <div id="navbar">
        <div class="navbar-content">
          <div class="slide-down-nav-link-container">
            <a class="slide-down-nav-link hover" href="/features"
              >Features</a
            >
            <a class="slide-down-nav-link hover" href="/playlists"
              >Playlists</a
            >
            <a class="slide-down-nav-link hover" href="/dictionary"
              >Dictionary</a
            >
            <a class="slide-down-nav-link hover" href="/about"
              >About</a
            >
          </div>

          <div class="slide-down-burger-menu">Menu</div>

          <div class="slide-down-nav-header hover">
            <NuxtLink to="/">
              <h1 id="slide-down-nav-punchline-punjabi">Punchline Punjabi</h1>
            </NuxtLink>
          </div>

          <div class="slide-down-nav-social-icons-container">
            <div class="slide-down-social-links">
              <a class="slide-down-social-icons" href="#"
                ><img
                  id="insta-svg"
                  src="../assets/svg/instagram.svg"
                  alt="punchline punjabi instagram icon"
              /></a>
              <!--<a class="slide-down-social-icons" href="#"
                ><img
                  src="dist/svg icons/twitter white logo.svg"
                  alt="punchline punjabi twitter icon"
              /></a>-->
              <a class="slide-down-social-icons" href="#"
                ><img
                  src="../assets/svg/youtube.svg"
                  alt="punchline punjabi youtube icon"
              /></a>
              <!--<a class="slide-down-social-icons" href="#"
                ><img
                  src="dist/svg icons/genius icon.svg"
                  alt="punchline punjabi genius icon"
              /></a>-->
            </div>
          </div>
        </div>
      </div>
      </div>
</template>

<script>

</script>
