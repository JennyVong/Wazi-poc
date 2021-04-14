<template>
  <div id="home">
    <header>
      <div>
        <Navbar />
      </div>
      <!-- Nav Bar -->
    </header>
    <main>
      <div class="homepage">
        <div class="py-5">
          <Carousel :cards="cards" />
        </div>
        <div class="py-5">
          <UpcomingSessions :totalSessions="totalSessions" :session="session" />
        </div>
        <div class="py-5">
          <Articles />
        </div>
      </div>
    </main>
    <footer>
      <Footer />
    </footer>
    <!-- <Logo /> -->
  </div>
</template>

<script>
import Carousel from '../components/carousel/Carousel'
import UpcomingSessions from '../components/UpcomingSessions'

export default {
  name: 'Home',
  components: { Carousel, UpcomingSessions },
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
      totalSessions: 1,
      session: {
        therapist: 'Therapist',
        sessionType: 'Zoom',
        date: {
          month: 'Mar',
          day: '18',
          year: '2021',
        },
        time: '12:00 PM',
        timezone: 'EST',
      },
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
