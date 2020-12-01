<template>
  <div>
    <section class="hero is-info is-small">
      <div class="hero-body">
        <div class="container has-text-centered">
          <p class="title">Nuxt JS</p>
          <p class="subtitle">Server Side Rendering</p>
        </div>
      </div>
    </section>
    <div class="box cta">
      <p class="has-text-centered">NuxtJS Server Side Rendering examples.</p>
    </div>
    <section class="container">
      <div class="columns is-multiline">
        <div v-for="post in posts" :key="post.id" class="column is-one-quarter">
          <div class="card">
            <div class="card-image">
              <figure class="image is-4by3">
                <img :src="post.image" :alt="post.title" />
              </figure>
            </div>
            <div class="card-content">
              <p class="title is-4">
                <nuxt-link :to="`/post/${post.id}`">{{ post.title }}</nuxt-link>
              </p>
              <div class="content">{{ post.description }}</div>
              <div class="buttons is-right">
                <nuxt-link
                  :to="`/post/${post.id}`"
                  class="button is-link is-right"
                  >Read More</nuxt-link
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get(`http://localhost:8000/posts`);
    return {
      posts,
    };
  },
};
</script>

<style></style>
