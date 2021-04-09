<template>
  <div
    class="flex flex-col p-4 rounded-xl w-5/6 shadow-md hover:shadow-2xl transition-all"
    style="height: 60vh"
  >
    <img :src="article.cover" class="h-1/2 rounded-xl" />
    <h1 class="text-left py-2">{{ article.title }}</h1>
    <p
      class="text-left flex-grow overflow-hidden overflow-ellipsis text-gray-500 pb-2"
    >
      {{ article.description }}
    </p>
    <button
      class="bg-primary-50 hover:bg-primary-500 text-primary-700 font-semibold hover:text-white mt-2 py-2 px-4 border border-primary-500 hover:border-transparent rounded transition-all"
    >
      More Info
    </button>
  </div>
</template>

<script>
export default {
  name: 'ArticleCard',
  props: {
    article: {
      type: Object,
      default: () => {
        return {
          title: 'Amazing Blog Article',
          cover:
            'https://images.unsplash.com/photo-1476514525535-07fb3b4ae5f1?ixid=MXwxMjA3fDB8MHxzZWFyY2h8OXx8dHJhdmVsfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut ',
        }
      },
    },
  },
}
</script>

<style scoped></style>
