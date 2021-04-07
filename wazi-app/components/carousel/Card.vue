<template>
  <div
    class="flex justify-center items-center mx-12 md:max-w-2xl text-gray-900"
  >
    <!-- Image -->
    <div class="relative">
      <transition class="slide">
        <img
          class="w-full object-cover object-center rounded-lg shadow-lg"
          :src="require(`@/assets/images/${imgName}`)"
          alt="dummy image"
        />
      </transition>

      <!-- Arrows -->
      <div class="absolute inset-y-0 left-0">
        <button
          class="mt-48 h-16 cursor-pointer duration-300 opacity-50 hover:opacity-10"
          @click="showPrevElement()"
        >
          <img
            class="h-16"
            :src="require(`@/assets/svg/left.svg`)"
            alt="left arrow"
          />
        </button>
      </div>
      <div class="absolute inset-y-0 right-0">
        <button
          class="mt-48 h-16 cursor-pointer duration-300 opacity-50 hover:opacity-10"
          @click="showNextElement()"
        >
          <img
            class="h-16"
            :src="require(`@/assets/svg/right.svg`)"
            alt="right arrow"
          />
        </button>
      </div>

      <!-- Button -->
      <div class="absolute inset-x-0 bottom-0 m-4">
        <a href="">
          <button
            class="text-lg p-2.5 font-medium rounded-xl duration-300 shadow bg-gray-300 bg-opacity-80 hover:bg-white"
          >
            {{ btnAction }}
          </button>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    imgName: String,
    btnAction: String,
    showPrevElement: Function,
    showNextElement: Function,
  },
}
</script>

<style scoped>
/* Transitions dont work! */
.slide-leave-active,
.slide-enter-active {
  opacity: 0;
  transition: 1s;
}
.slide-enter {
  /* transform: translate(100%, 0); */
  opacity: 0;
}
.slide-leave-to {
  opacity: 0;
}
</style>
