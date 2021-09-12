<template>
  <div>
    <nav>
      <ul>
        <li :class="{ 'py-2': link.depth === 2, 'ml-2 pb-2': link.depth === 3 }"
            v-for="link of article.toc" :key="link.id">
          <NuxtLink :to="`#${link.id}`">{{ link.text }}</NuxtLink>
        </li>
      </ul>
    </nav>

    <article>
    <h1>{{ article.title }}</h1>
      <p>{{ article.description }}</p>
      <img :src="article.img" :alt="article.alt" />
      <p>Article last updated: {{ formatDate(article.updatedAt) }}</p>

      <nuxt-content :document="article" />
    </article>
  </div>
</template>


<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()

    return { article }
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
  }
}
</script>

<style>

.icon.icon-link {
  background-image: url('~assets/svg/icon-hashtag.svg');
  display: inline-block;
  width: 20px;
  height: 20px;
  background-size: 20px 20px;
}

</style>
