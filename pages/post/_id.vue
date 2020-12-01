<template>
  <div>
    <Header :post="post" />
    <section class="container" style="margin-bottom: 50px;">
      <div class="notification">
        <img :src="post.image" :alt="post.title" />
        <div class="card-content">
          <p class="title is-4">{{ post.title }}</p>
          <div class="content">{{ post.description }}</div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Header from "../../components/Header";
export default {
  components: {
    Header,
  },
  async asyncData({ $axios, params, error }) {
    const post = await $axios.$get(`http://localhost:8000/posts/${params.id}`);

    return {
      post,
    };
  },
};
</script>

<style></style>
