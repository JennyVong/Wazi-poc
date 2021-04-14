<template>
  <!-- This example requires Tailwind CSS v2.0+ -->
  <nav class="bg-white w-full h-16">
    <div class="mx-auto px-2 sm:px-6 lg:px-8">
      <div class="relative flex items-center justify-between h-16">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <button
            type="button"
            class="v-on-clickaway='closeMenu' inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
            aria-controls="mobile-menu"
            aria-expanded="false"
            @click="menuOpen = !menuOpen"
          >
            <span class="sr-only">Open main menu</span>
            <!--
            Icon when menu is closed.
            Heroicon name: outline/menu
            Menu open: "hidden", Menu closed: "block"
          -->
            <svg
              class="block h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
            </svg>
            <!--
            Icon when menu is open.
            Heroicon name: outline/x
            Menu open: "block", Menu closed: "hidden"
          -->
            <svg
              class="hidden h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
        <div
          class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start"
        >
          <div class="flex-shrink-0 flex items-center">
            <img
              class="block lg:hidden h-8 w-auto"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-500.svg"
              alt="Wazi"
            />
            <img
              class="hidden lg:block h-8 w-auto"
              src="https://tailwindui.com/img/logos/workflow-logo-indigo-500-mark-white-text.svg"
              alt="Wazi"
            />
          </div>
          <div class="hidden md:flex space-x-10">
            <div class="relative">
              <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
              <a
                href="#"
                class="text-black hover:underline inline-flex hover:text-black px-3 py-2 rounded-md text-sm font-medium"
                aria-current="page"
                >Home</a
              >
              <!-- sessions dropdown -->
              <button
                type="button"
                class="v-on-clickaway='closeMenu' text-black group inline-flex hover:underline hover:text-black px-3 py-2 rounded-md text-sm font-medium focus:outline-none"
                @click="sessionsOpen = !sessionsOpen"
              >
                <span>Sessions</span>
                <svg
                  class="text-gray-400 ml-2 h-5 w-5 group-hover:text-gray-500"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  />
                </svg>
              </button>
              <transition
                enter-active-class="transition ease-out duration-100 transform"
                enter-class="opacity-0 scale-95"
                enter-to-class="opacity-100 scale-100"
                leave-active-class="transition ease-in duration-75 transform"
                leave-class="opacity-100 scale-100"
                leave-to-class="opacity-0 scale-95"
              >
                <div
                  v-show="sessionsOpen"
                  class="z-10 absolute mt-2 w-48 rounded-md shadow-lg py-1 bg-white focus:outline-none"
                  role="menu"
                  aria-orientation="vertical"
                  aria-labelledby="user-menu"
                >
                  <a
                    to="#"
                    class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                    role="menuitem"
                    >Book a Session</a
                  >
                  <a
                    to="#"
                    class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                    role="menuitem"
                    >Upcoming Sessions</a
                  >
                  <a
                    href="#"
                    class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                    role="menuitem"
                    >View all Sessions</a
                  >
                </div>
              </transition>
              <!-- assessments dropdown -->
              <button
                type="button"
                class="v-on-clickaway='closeMenu' text-black group inline-flex hover:underline hover:text-black px-3 py-2 rounded-md text-sm font-medium focus:outline-none"
                @click="assessmentsOpen = !assessmentsOpen"
              >
                <span>Assessments</span>
                <svg
                  class="text-gray-400 ml-2 h-5 w-5 group-hover:text-gray-500"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  />
                </svg>
              </button>
              <transition
                enter-active-class="transition ease-out duration-100 transform"
                enter-class="opacity-0 scale-95"
                enter-to-class="opacity-100 scale-100"
                leave-active-class="transition ease-in duration-75 transform"
                leave-class="opacity-100 scale-100"
                leave-to-class="opacity-0 scale-95"
              >
                <div
                  v-show="assessmentsOpen"
                  class="z-10 absolute right-1 mt-2 w-48 rounded-md shadow-lg py-1 bg-white focus:outline-none"
                  role="menu"
                  aria-orientation="vertical"
                  aria-labelledby="user-menu"
                >
                  <a
                    to="#"
                    class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                    role="menuitem"
                    >Take an Assessment</a
                  >
                  <a
                    to="#"
                    class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                    role="menuitem"
                    >View Assessments</a
                  >
                </div>
              </transition>
              <a
                href="#"
                class="text-black hover:underline hover:text-black px-3 py-2 rounded-md text-sm font-medium"
                >Articles</a
              >
            </div>
          </div>
        </div>
        <div
          class="absolute inset-y-0 right-0 flex items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0"
        >
          <button
            class="text-black hover:text-teal rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-300 focus:ring-white"
          >
            <span class="sr-only">View notifications</span>
            <!-- Heroicon name: outline/bell -->
            <svg
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
              />
            </svg>
          </button>
          <!-- Profile dropdown -->
          <div class="ml-3 relative v-on-clickaway='closeMenu'">
            <div>
              <button
                type="button"
                class="flex text-sm rounded-full focus:outline-none"
                aria-expanded="false"
                @click="isOpen = !isOpen"
              >
                <span class="sr-only">Open user menu</span>
                <img
                  class="h-8 w-8 rounded-full"
                  src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
                  alt=""
                />
                <svg
                  class="text-gray-400 ml-2 h-5 w-5 group-hover:text-gray-500"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  />
                </svg>
              </button>
            </div>
            <!--
            Dropdown menu, show/hide based on menu state.
            Entering: "transition ease-out duration-100"
              From: "transform opacity-0 scale-95"
              To: "transform opacity-100 scale-100"
            Leaving: "transition ease-in duration-75"
              From: "transform opacity-100 scale-100"
              To: "transform opacity-0 scale-95"
          -->
            <transition
              enter-active-class="transition ease-out duration-100 transform"
              enter-class="opacity-0 scale-95"
              enter-to-class="opacity-100 scale-100"
              leave-active-class="transition ease-in duration-75 transform"
              leave-class="opacity-100 scale-100"
              leave-to-class="opacity-0 scale-95"
            >
              <div
                v-show="isOpen"
                class="z-10 origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg py-1 bg-white ring-1 ring-black ring-opacity-5 focus:outline-none"
                role="menu"
                aria-orientation="vertical"
                aria-labelledby="user-menu"
              >
                <a
                  to="#"
                  class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                  role="menuitem"
                  >My account</a
                >
                <a
                  to="#"
                  class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                  role="menuitem"
                  >App Settings</a
                >
                <a
                  href="#"
                  class="block px-4 py-2 text-sm text-teal hover:bg-gray-100"
                  role="menuitem"
                  >Sign out</a
                >
              </div>
            </transition>
          </div>
        </div>
      </div>
    </div>
    <!-- Mobile menu, show/hide based on menu state. -->
    <div
      id="mobile-menu"
      class="z-30 v-on-clickaway='menuOpen'"
      v-show="menuOpen"
    >
      <div
        v-show="menuOpen"
        class="z-10 absolute left-0 mt-2 w-full rounded-md shadow-lg py-1 bg-white ring-1 ring-black ring-opacity-5 focus:outline-none"
        role="menu"
        aria-orientation="vertical"
        aria-labelledby="user-menu"
      >
        <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
        <a
          href="#"
          class="hover:bg-gray-100 text-teal block px-3 py-2 rounded-md text-base font-medium"
          aria-current="page"
          >Home</a
        >
        <a
          href="#"
          class="text-teal hover:bg-gray-100 block px-3 py-2 rounded-md text-base font-medium"
          >Book a Session</a
        >
        <a
          href="#"
          class="text-teal hover:bg-gray-100 block px-3 py-2 rounded-md text-base font-medium"
          >Upcoming Sessions</a
        >
        <a
          href="#"
          class="text-teal hover:bg-gray-100 block px-3 py-2 rounded-md text-base font-medium"
          >View All Sessions</a
        >
        <a
          href="#"
          class="text-teal hover:bg-gray-100 block px-3 py-2 rounded-md text-base font-medium"
          >Take an Assessment</a
        >
        <a
          href="#"
          class="text-teal hover:bg-gray-100 block px-3 py-2 rounded-md text-base font-medium"
          >View Assessments</a
        >
        <a
          href="#"
          class="text-teal hover:bg-gray-100 block px-3 py-2 rounded-md text-base font-medium"
          >Articles</a
        >
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data: () => ({
    isOpen: false,
    menuOpen: false,
    sessionsOpen: false,
    assessmentsOpen: false,
  }),
}
</script>
