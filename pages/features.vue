<template>
  <div id="page-container">
  <MobNav />
  <Sub :subTitle="this.sub.subTitle" :subContent="this.sub.subContent"/>
  <MoreMusic />
  <Footer />
  </div>
</template>

<script>
import Sub from '../components/Sub.vue'
import MobNav from '../components/MobNav.vue'
import MoreMusic from '../components/MoreMusic.vue'
import Footer from '../components/Footer.vue'
import '~/assets/scss/style.scss'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    MobNav,
    Sub,
    MoreMusic,
    Footer
  },
  data() {
    return {
      sub:{
        subTitle: 'Features',
        subContent: 'The features section is dedicated to our favourite Punjabi artists, past and present. Here, you\'ll find music releases, reviews, and the stories behind the top Punjabi songs in 2020 and prior. Stay in the loop with our flagship series: Sonah Selectah, which filters and showcases gold standard Punjabi music through thoughtful storytelling and reviewing; our priority will always be innovation.'
      }
      }
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
