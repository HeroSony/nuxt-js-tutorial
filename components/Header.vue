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
    <div class="container box">
      <nav class="breadcrumb" aria-label="breadcrumbs">
        <ul>
          <li>
            <nuxt-link to="/">Home</nuxt-link>
          </li>
          <li class="is-active">
            <a href="#" aria-current="page">{{post.title}}</a>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>


<script lang="ts">
export default {
  props: ["post"],
};
</script>