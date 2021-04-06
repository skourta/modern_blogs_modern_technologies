<template>
  <div class="blog_contauiner">
    <blog-card></blog-card>
    <blog-card></blog-card>
    <blog-card></blog-card>
    <blog-card></blog-card>
  </div>
</template>

<script>
import BlogCard from '~/components/Global/BlogCard.vue'
export default {
  components: { BlogCard },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.blog_contauiner {
  @apply flex flex-col items-center md:flex-row gap-4 md:flex-wrap justify-between overflow-hidden p-4;
  :last-child {
    @apply md:mr-auto;
  }
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
