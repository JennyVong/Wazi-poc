<template>
  <div id="home" class="container">
    <header>
      <div>
        <Navbar />
      </div>
      <!-- Nav Bar -->
      <!-- <navbar /> -->
    </header>
    <main>
      <div class="homepage">
        <div>
          <Carousel :cards="cards" />
        </div>
        <div>
          <UpcomingSessions :totalSessions="totalSessions" :session="session" />
        </div>
        <div class="mt-10">
          <Articles />
        </div>
      </div>
    </main>

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
        sessionType: 'Type',
        date: 'Date',
        time: 'Time',
        timezone: 'Timezone',
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
