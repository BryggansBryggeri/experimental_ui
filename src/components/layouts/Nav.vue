<template>
  <nav>
    <div
      id="Navbar"
      class="
        relative
        z-50
        flex flex-row
        items-center
        justify-between
        w-full
        px-6
        py-3
        mx-auto
        mb-4
        align-middle
        bg-white
        border-t-2 border-green-800
        shadow-lg
        dark:bg-gray-900
      "
    >
      <h4 class="text-xl font-bold leading-tight underline logo">
        BryggIO
      </h4>
      <div class="flex flex-row items-center space-x-6 text-sm">
        <button
          class="
            flex flex-row
            space-x-2
            transition
            duration-150
            ease-in-out
            rounded
            focus:outline-none
            hover:text-indigo-400
          "
          @click="toggle"
        >
          <ArrowsExpandIcon class="w-5 h-5" />
        </button>
        <button
          class="focus:outline-none focus:ring-0"
          @click="toggleDark()"
        >
          <div
            v-if="isDark"
            class="transition duration-150 hover:text-yellow-600"
          >
            <SunIcon class="w-6 h-6" />
          </div>
          <div
            v-else
            class="transition duration-150 hover:text-indigo-400"
          >
            <MoonIcon class="w-6 h-6" />
          </div>
        </button>
        <router-link
          class="
            flex flex-row
            space-x-2
            transition
            duration-150
            ease-in-out
            rounded
            focus:outline-none
            hover:text-indigo-400
          "
          to="/library"
        >
          <BookmarkIcon class="w-5 h-5" />
          <p>Library</p>
        </router-link>
        <router-link
          class="
            flex flex-row
            space-x-2
            transition
            duration-150
            ease-in-out
            rounded
            focus:outline-none
            hover:text-indigo-400
          "
          to="/"
        >
          <ViewBoardsIcon class="w-5 h-5" />
          <p>Home</p>
        </router-link>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import {
  SunIcon,
  MoonIcon,
  ArrowsExpandIcon,
  ViewBoardsIcon,
  BookmarkIcon,
} from "@heroicons/vue/outline";
import { useDark, useToggle, useFullscreen } from "@vueuse/core";

const { toggle } = useFullscreen();

const isDark = useDark();
const toggleDark = useToggle(isDark);
</script>
