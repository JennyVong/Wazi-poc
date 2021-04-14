<template>
  <div class="">
    <h1 class="text-center text-xl font-bold pt-7">Upcoming Sessions</h1>
    <!-- No sessions -->
    <div
      v-if="totalSessions === 0"
      class="rounded-lg w-4/5 h-28 mx-auto my-8 md:max-w-2xl"
    >
      <div class="text-center text-black p-6">
        <p>
          You have no upcoming sessions! Start by
          <a href="#" class="duration-300 underline hover:text-teal"
            >booking a session</a
          >
        </p>
      </div>
    </div>

    <!-- Upcoming session -->
    <div
      v-else
      class="relative bg-articlespace rounded-lg w-4/5 h-28 mx-auto mt-8 mb-16 ring-2 ring-teal shadow-lg md:max-w-2xl"
    >
      <!-- Profile -->
      <div class="absolute inset-y-0 pl-5 pt-2 md:pl-10 md:pt-6">
        <img
          class="h-14 w-14 rounded-full"
          src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
        />
      </div>

      <div
        class="text-left text-black pl-24 py-2 flex-col -space-y-1.5 md:py-5 md:pl-32"
      >
        <div class="pb-1 md:text-lg">
          {{ session.therapist }} // Via {{ session.sessionType }}
        </div>
        <div class="text-sm md:text-base">
          {{ session.date.month }} {{ session.date.day }},
          {{ session.date.year }}
        </div>
        <div class="text-sm md:text-base">
          {{ session.time }} - {{ session.timezone }}
        </div>
      </div>
      <!-- Button -->
      <div
        class="text-center absolute inset-x-0 bottom-3 md:text-right md:pr-16 md:bottom-8"
      >
        <button
          class="pt-0.5 text-sm pb-0.5 px-6 rounded-lg shadow duration-300 shadow bg-teal hover:bg-opacity-75 md:text-base md:py-2.5 md:px-16"
        >
          <div class="text-white font-normal">View Details</div>
        </button>
      </div>

      <div class="text-center mt-14 md:mt-6">
        <a href="#" class="text-gray-500 duration-300 hover:text-teal"
          >View all sessions ></a
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Upcoming-sessions',
  props: {
    totalSessions: Number,
    session: Object,
  },
}
</script>
