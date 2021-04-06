<template>
  <ul>
    <li v-for="(_, index) in elements" class="inline-block" :key="index">
      <button
        class="relative cursor-pointer m-1.5 mt-5 h-2.5 w-2.5 rounded-full bg-black opacity-20 duration-300 hover:opacity-10"
        :class="{ 'dot-selected': currentElementIndex === index }"
        @click="showElement(index)"
        :disabled="currentElementIndex === index"
      />
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Indicators',
  props: {
    elements: Array,
    currentElementIndex: Number,
    showElement: Function,
  },
}
</script>

<style scoped>
.dot-selected {
  opacity: 0.7;
  cursor: default;
}
</style>
