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
        class="md:flex md:flex-row z-10 relative transition-all"
      >
        <li class="pr-5"><a> Services </a></li>
        <li class="pr-5"><a>Porfolio</a></li>
        <li class="pr-5"><a>About</a></li>
        <li><a>Contact</a></li>
      </ul>
    </transition>
  </header>
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

<style lang="scss" scoped></style>
