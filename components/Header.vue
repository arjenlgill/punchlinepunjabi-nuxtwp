<template>
  <header id="header-nav">
    <div class="social-icons-wrapper-for-desktop">
      <div class="connect-with-us-div-block">
        <span id="connect-with-us-text">Connect with us:</span>
      </div>

      <div class="social-icons-div-block-desktop">
        <a href="#"
          ><img
            id="insta-svg"
            src='~/assets/svg/instagram.svg'
            alt="punchline punjabi instagram icon"
        /></a>
        <!--<a href="#"
              ><img
                src="dist/svg icons/twitter white logo.svg"
                alt="punchline punjabi twitter icon"
            /></a>-->
        <a href="#"
          ><img
            src='~/assets/svg/youtube.svg'
            alt="punchline punjabi youtube icon"
        /></a>
        <!--<a href="#"
              ><img
                src="dist/svg icons/genius icon.svg"
                alt="punchline punjabi genius icon"
            /></a>-->
      </div>
    </div>

    <div class="brand-script-logo">
      <NuxtLink to="/">
      <span>Punchline</span> <br />
        <span id="punjabi">Punjabi</span>
      </NuxtLink>
    </div>

    <div class="desktop-nav-menu-wrapper">
      <NuxtLink to="/features">
      <span class="hover" id="features">Features</span>
      </NuxtLink>     
      <NuxtLink to="/playlists">
      <span class="hover" id="playlists">Playlists</span>
      </NuxtLink>
      <NuxtLink to="/dictionary">
      <span class="hover" id="Dictionary">Dictionary</span>
      </NuxtLink>
      <NuxtLink to="/about">
      <span class="hover" id="about">About</span>
      </NuxtLink>
    </div>

    <div class="burger-menu">Menu</div>
  </header>
</template>