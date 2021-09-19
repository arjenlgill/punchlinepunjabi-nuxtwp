<template>
  <div id="page-container">
  <MobNav />
  <div id="post-wrapper">
    <div class="post-img-container">
      <img v-bind:src="post.featured_image_url" alt="" class="post-img" />
    </div>

    <div class="post-content-container">
      <div id="tte">
        <h1 class="post-h1" v-html="post.title.rendered"> </h1>

        <h2 class="post-h2">{{ this.post.postH2 }}</h2>

        <p class="post-intro">{{ postIntro }}</p>

        <div v-bind:key="lyric" v-for="(lyric, index) in lyrics">
          <p v-if="index % 2 === 0" class="lyrics-og">
            {{ lyric }}
          </p>

          <p v-else class="lyrics-trans">{{ lyric }}</p>
        </div>

        <p class="post-content" v-html="post.content.rendered"></p>
  
      </div>
    </div>
  </div>

  <MoreMusic />
  <Footer />
  </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
                post: {}
            }
        },
        async asyncData({params, payload}) {
            if(payload) {
                return {
                    post: payload
                }
            } else {
                return axios.get('http://punchlinepunjabi.local/punchlinepunjabi/wp-json/wp/v2/posts/' + params.id)
                    .then((res) => {
                        return {
                            post: res.data
                        }
                    })
            }
        }
    }
</script>