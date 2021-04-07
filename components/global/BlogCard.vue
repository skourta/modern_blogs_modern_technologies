<template>
  <div
    class="bg-white w-4/5 shadow-sm hover:shadow-xl transition-all flex flex-col p-4 rounded-lg md:max-w-xs"
    style="height: 60vh"
  >
    <img
      class="w-full h-1/2 object-cover rounded-lg m-0"
      :src="blog.cover"
      alt="cover image"
    />
    <div class="flex flex-col gap-3 items-start h-1/2 py-4">
      <h3 class="font-bold m-0">{{ blog.name }}</h3>
      <p
        class="flex-grow overflow-hidden overflow-ellipsis text-justify text-sm"
      >
        {{ blog.description }}
      </p>
      <button
        class="bg-blue-100 px-4 py-2 text-xs font-semibold tracking-wider text-blue-600 rounded hover:bg-blue-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2"
        @click="$nuxt.$router.push('/posts/test')"
      >
        See More
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlogCard',
  props: {
    blog: {
      type: Object,
      default: () => {
        return {
          name: 'Awesome Blog Post',
          cover:
            'https://images.unsplash.com/photo-1476900543704-4312b78632f8?ixid=MXwxMjA3fDB8MHxzZWFyY2h8M3x8dHJhdmVsfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
        }
      },
    },
  },
}
</script>

<style lang="scss" scoped></style>
