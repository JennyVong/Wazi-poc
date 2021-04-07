<template>
  <div id="home" class="container">
    <header>
      <!-- <h1>Nav Bar</h1> -->
      <!-- Nav Bar -->
    </header>
    <main>
      <div class="homepage">
        <div>
          <Carousel :cards="cards" />
        </div>
        <div>
          <Articles />
        </div>
      </div>
    </main>

    <!-- <Logo /> -->
  </div>
</template>

<script>
import Carousel from '../components/carousel/Carousel'
export default {
  name: 'Home',
  components: { Carousel },
  data() {
    return {
      cards: [
        {
          imgName: 'dummyImg2.jpg',
          btnAction: 'Book a session',
        },
        {
          imgName: 'dummyImg3.jpg',
          btnAction: 'View all sessions',
        },
        {
          imgName: 'dummyImg4.jpg',
          btnAction: 'Take an assessment',
        },
        {
          imgName: 'dummyImg5.jpg',
          btnAction: 'View assessments',
        },
      ],
    }
  },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
