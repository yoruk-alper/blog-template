<template>
  <div class="m-4">
    <h1 class="font-bold text-2xl mb-1">Blog Posts</h1>
    <ul class="flex flex-wrap">
      <li v-for="article of articles" :key="article.slug" class="xs:w-full md:w-1/2 px-2 xs:mb-6 md:mb-12 article-card">
        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <img :src="article.img" class="h-48 xxlmin:w-1/2 xxlmax:w-full object-cover"/>
          <div>
            <h2>{{ article.title }}</h2>
            <p>by {{ article.author.name }}</p>
            <p>{{ article.description }}</p>
          </div>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>


<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('articles')
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles
    }
  }
}
</script>
<style class="postcss">
.article-card {
  border-radius: 8px;
}
.article-card a {
  background-color: #fff;
  border-radius: 8px;
}
.article-card img div {
  border-radius: 8px 0 0 8px;
}
</style>
