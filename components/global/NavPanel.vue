<template>
  <header
    v-if="$device.isMobile"
    class="h-16 flex flex-col py-4 items-center text-xl font-sans font-bold"
    v-click-outside="closeMenu"
  >
    <p @click="showMenu = !showMenu">Modern Blog</p>
    <transition name="fade">
      <ul
        v-if="showMenu"
        class="flex flex-col bg-white shadow-xl p-4 rounded z-10 relative items-center justify-center"
      >
        <li class="nav_link"><a> Services </a></li>
        <li class="nav_link"><a>Porfolio</a></li>
        <li class="nav_link"><a>About</a></li>
        <li class="nav_link"><a>Contact</a></li>
      </ul>
    </transition>
  </header>

  <aside
    v-else
    class="w-1/5 flex flex-col py-4 m-2 items-center text-xl font-sans font-bold"
  >
    <p class="mb-4">Modern Blog</p>
    <ul
      class="flex flex-col font-bold p-4 rounded items-center justify-center w-full"
    >
      <li class="nav_link"><a> Services </a></li>
      <li class="nav_link"><a>Porfolio</a></li>
      <li class="nav_link"><a>About</a></li>
      <li class="nav_link"><a>Contact</a></li>
    </ul>
  </aside>
</template>

<script>
export default {
  name: 'NavPanel',
  data() {
    return {
      showMenu: false,
    }
  },
  methods: {
    closeMenu() {
      console.log('test')
      this.showMenu = false
    },
  },
}
</script>

<style scoped>
.nav_link {
  @apply py-2 hover:text-primary-600 cursor-pointer;
}
</style>
