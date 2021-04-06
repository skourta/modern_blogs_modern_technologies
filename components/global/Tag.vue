<template>
  <span
    class="bg-yellow-200 text-yellow-700 px-2 py-0.5"
    style="width: fit-content"
  >
    {{ text }}
  </span>
</template>

<script>
export default {
  name: 'Tag',
  props: {
    text: {
      type: String,
      default: 'Tag',
    },
  },
}
</script>

<style lang="scss" scoped></style>
