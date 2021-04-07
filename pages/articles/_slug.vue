<template>
  <div class="flex flex-col items-center gap-8 px-8 md:px-40 py-12">
    <div class="flex gap-2 justify-center">
      <tag
        v-for="(tag, index) in article.tags"
        :text="tag"
        :key="`tag_${index}`"
      ></tag>
    </div>
    <h1 class="title text-center">{{ article.name }}</h1>
    <div class="flex flex-col items-center">
      <h2>{{ article.author.name }}</h2>
      <h2 class="text-gray-500">
        {{ article.date }}
      </h2>
    </div>
    <div class="relative flex flex-col items-center w-full h-96 md:h-screen">
      <img
        class="absolute w-full bottom-0 object-cover rounded-lg"
        style="height: calc(100% - 3rem)"
        :src="article.cover"
      />
      <img
        class="rounded-full w-24 h-24 border-white border-4 relative z-10"
        :src="article.author.image"
        alt="author image"
      />
    </div>
    <article>
      <nuxt-content class="prose lg:prose-xl" :document="article" />
    </article>
  </div>
</template>

<script>
import Tag from '~/components/Global/Tag.vue'
export default {
  components: { Tag },
  name: 'PostPage',
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()

    return { article }
  },
}
</script>

<style lang="scss" scoped></style>
