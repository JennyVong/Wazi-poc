<template>
  <div id="home" class="container">
    <header>
      <!-- <h1>Nav Bar</h1> -->
      <!-- Nav Bar -->
    </header>
    <main>
      <div class="section">
        <Carousel :cards="cards" />
      </div>
    </main>

    <!-- <Logo /> -->

    <!-- <Indicators /> -->
    <!-- <h1 class="title">wazi-app</h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a> -->
    <!-- </div> -->
  </div>
</template>

<script>
import Carousel from '../components/Carousel'
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
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
