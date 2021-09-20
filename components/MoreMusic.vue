<template>
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
                <h3 class="cms-text-block-header" v-html="post.title.rendered">
                </h3>

                <div class="cms-paragraph" v-html="post.excerpt.rendered">
                </div>

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
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>

<script>

export default {
  data: function () {
    return {
    };
  },
  props: ['posts'],
  computed: {
      posts() {
          return this.$store.state.posts
      }
  }
};
</script>