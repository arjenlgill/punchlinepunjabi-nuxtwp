<template>
  <div id="page-container">
  <BurgerMenu />
  <Header />
  <MobNav />
  <HHero />
  <Footer />
    <section>
      <div class="main-container">
        <div class="main-section-heading">
          <h2 id="main-section-heading-h2">Latest Music Content</h2>
        </div>

        <div class="grid-wrap">
          <div class="cms-wrapper">
            <!--cms item-->
            <div
              v-bind:key="post"
              v-for="post in posts"
              class="cms-item-container"
            >
              <nuxt-link :to="{ name: 'blog-slug', params: { slug: post.slug, id: post.id } }">
                <img v-bind:src="post.featured_image_url" class="cms-card-image" alt="punchline punjabi thumbnail image">

                <div class="cms-text-block">
                  <h3 class="cms-text-block-header">
                    {{ post.title.rendered }}
                  </h3>

                  <p class="cms-paragraph">
                    {{ post.title.rendered }}
                  </p>

                  <div class="category-subcat-wrapper">
                    <div class="cms-category">Features</div>

                    <div class="cms-sub-category">Lyrics</div>
                  </div>
                </div>
              </nuxt-link>
            </div>
          </div>
        </div>

        <!--cms section end-->

        <div class="newsletter-form-signup">
          <form class="newsletter-form-container" action="/form.js">
            <label for="newsletter-form" id="form-text-paragraph"
              >Stay informed of our latest drops by subscribing to our
              newsletter</label
            >
            <input
              type="text"
              name="newsletter-form"
              id="form-text-input"
              placeholder="type in e-mail and hit 'enter'"
            />
          </form>
        </div>
      </div>
  </section>
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
            return axios.get('http://punchlinepunjabi.local/punchlinepunjabi/wp-json/wp/v2/posts/').then((res) => {
                store.commit('frontPagePosts', res.data)
            }).catch((error) => {
                console.log(error)
            })
        },
        computed: {
            posts() {
                return this.$store.state.posts
            }
        }
    }
</script>
