<template>
  <div class="flex flex-col items-center gap-8 px-8 md:px-40 py-12">
    <div class="flex gap-2 justify-center">
      <tag
        v-for="(tag, index) in post.tags"
        :text="tag"
        :key="`tag_${index}`"
      ></tag>
    </div>
    <h1 class="title text-center">{{ post.name }}</h1>
    <div class="flex flex-col items-center">
      <h2>{{ post.author.name }}</h2>
      <h2 class="text-gray-500">
        {{ post.date }}
      </h2>
    </div>
    <div class="relative flex flex-col items-center w-full h-96 md:h-screen">
      <img
        class="absolute w-full bottom-0 object-cover rounded-lg"
        style="height: calc(100% - 3rem)"
        :src="post.cover"
      />
      <img
        class="rounded-full w-24 h-24 border-white border-4 relative z-10"
        :src="post.author.image"
        alt="author image"
      />
    </div>
  </div>
</template>

<script>
import Tag from '~/components/Global/Tag.vue'
export default {
  components: { Tag },
  name: 'PostPage',
  props: {
    post: {
      type: Object,
      default: () => {
        return {
          name: 'Awesome Blog Post',
          cover:
            'https://images.unsplash.com/photo-1476900543704-4312b78632f8?ixid=MXwxMjA3fDB8MHxzZWFyY2h8M3x8dHJhdmVsfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          author: {
            name: 'Israa Guermat',
            image:
              'https://scontent.falg2-2.fna.fbcdn.net/v/t1.6435-1/p200x200/168295242_1399529377055575_5677355426657111566_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=dbb9e7&_nc_eui2=AeGhpdokgIfrriAwwQmrvvz4nLiP9uR6chicuI_25HpyGMy2QT37DsBzYTHTop4Y1Pj6aLqDZyftqfNi8sTxLfNu&_nc_ohc=f3SjXfQN2rcAX-xonP_&_nc_ad=z-m&_nc_cid=1216&_nc_pt=1&_nc_ht=scontent.falg2-2.fna&tp=6&oh=46c6992ba97ac1adf4b9b062d6a9dc47&oe=6093E057',
          },
          date: new Date().toLocaleDateString(undefined, {
            year: 'numeric',
            month: 'long',
            day: 'numeric',
          }),
          tags: ['Traveling', 'Amazing places'],
        }
      },
    },
  },
}
</script>

<style lang="scss" scoped></style>
