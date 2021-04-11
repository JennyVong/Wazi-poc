<template>
  <div class="text-center pt-7">
    <div class="inline-block">
      <Card
        class="current-element"
        :imgName="currentElement.imgName"
        :btnAction="currentElement.btnAction"
        :showElement="this.showElement"
        :showNextElement="this.showNextElement"
        :showPrevElement="this.showPrevElement"
      />
    </div>

    <!-- Indicators -->
    <div>
      <ul>
        <li v-for="(_, index) in this.cards" class="inline-block" :key="index">
          <button
            class="relative cursor-pointer m-1.5 mt-3 h-2.5 w-2.5 rounded-full shadow bg-black opacity-20 duration-300 hover:opacity-10"
            :class="{ 'dot-selected': currentElementIndex === index }"
            @click="showElement(index)"
            :disabled="currentElementIndex === index"
          />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Card from './Card.vue'
export default {
  name: 'Carousel',
  props: { cards: Array },
  components: { Card },
  data() {
    return {
      currentElementIndex: 0,
    }
  },
  computed: {
    currentElement() {
      return this.cards[this.currentElementIndex]
    },
  },
  methods: {
    showNextElement() {
      if (this.currentElementIndex === this.cards.length - 1) {
        this.currentElementIndex = 0
      } else {
        this.currentElementIndex++
      }
    },
    showPrevElement() {
      if (this.currentElementIndex === 0) {
        this.currentElementIndex = this.cards.length - 1
      } else {
        this.currentElementIndex--
      }
    },
    showElement(elementIndex) {
      this.currentElementIndex = elementIndex
    },
  },
  mounted() {
    setInterval(() => {
      this.showNextElement()
    }, 5000)
  },
}
</script>

<style scoped>
.dot-selected {
  opacity: 0.7;
  cursor: default;
}

.slide-leave-active,
.slide-enter-active {
  transition: 3s;
}
.slide-enter {
  transform: translate(100%, 0);
}
.slide-leave-to {
  transform: translate(-100%, 0);
}
</style>
