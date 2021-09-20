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
        subTitle: 'Dictionary',
        subContent: ' We\'re developing an app that\'ll allow you to translate any Punjabi Roman Script word (Punjabi words that\'re spelled with the alphabet) into their English meanings. This app seeks to give you a closer connection to any Punjabi song you\'re interested in learning about, and will be completely accessible for anyone that doesn\'t know Punjabi Roman Script or Punjabi. Try typing \'jaikara\' into the search box below and click the word once the suggestion box appears.'
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
