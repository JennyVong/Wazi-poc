<template>
  <div class="text-center">
    <h1 class="font-bold pt-7">Upcoming Sessions</h1>
    <!-- No sessions -->
    <div class="container bg-articlespace rounded-2xl w-72 h-28 mx-auto my-8">
      <div class="text-center text-black p-6">
        <a> You have no upcoming sessions! Start by booking your session </a>
      </div>
    </div>

    <!-- Upcoming session -->
    <div
      class="container bg-articlespace rounded-2xl w-72 h-28 mx-auto my-8 ring-2 ring-teal shadow-md"
    >
      <div class="text-left text-black pl-24 py-2 flex-col -space-y-1.5">
        <div>Therapist // Type</div>
        <div>Date</div>
        <div>Time - Timezone</div>
      </div>

      <!-- Button -->
      <div class="inset-x-0 bottom-0 pl-7">
        <button
          class="pt-0.5 pb-0.5 pl-6 pr-6 rounded-xl duration-300 shadow bg-teal bg-opacity-80"
        >
          <div class="text-white text-sm font-normal">view details</div>
        </button>
      </div>

      <!-- Profile -->
      <div class="top-0 pl-5">
        <img
          class="h-14 w-14 rounded-full"
          src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
        />
      </div>
    </div>
  </div>
</template>
