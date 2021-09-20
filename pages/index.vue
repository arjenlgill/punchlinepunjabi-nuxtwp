<template>
  <div id="page-container">
  <BurgerMenu />
  <Header />
  <MobNav />
  <HHero />
  <MoreMusic />
  <Footer />
  </div>
</template>

<script>
import BurgerMenu from '../components/BurgerMenu.vue'
import Header from '../components/Header.vue'
import HHero from '../components/HHero.vue'
import MobNav from '../components/MobNav.vue'
import MoreMusic from '../components/MoreMusic.vue'
import Footer from '../components/Footer.vue'
import '~/assets/scss/style.scss'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    MobNav,
    HHero,
    MoreMusic,
    Footer,
    BurgerMenu
  },
  fetch({ store }) {
    return axios.get('http://punchlinepunjabi.local/punchlinepunjabi/wp-json/wp/v2/posts?per_page=100').then((res) => {
        store.commit('frontPagePosts', res.data)
    }).catch((error) => {
        console.log(error)
    })
  },
}
</script>
