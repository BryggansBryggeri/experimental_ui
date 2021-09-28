<template>
  <div class="container flex flex-wrap mx-auto overflow-hidden">
    <div class="w-1/4 p-5 my-5 overflow-hidden bg-gray-400">
      <Toggle />
      <!-- Todo: Emits, Common types such as On/Off Man/Auto etc? -->
    </div>

    <div class="w-1/4 p-5 my-5 overflow-hidden bg-gray-100">
      <DoubleLabelToggle
        left-label="Manual"
        right-label="Auto"
      />
      Value is {{ toggleValue1 }}
      <!-- Todo: Emits, Common types such as On/Off Man/Auto etc? -->
    </div>

    <div class="w-1/4 p-5 my-5 overflow-hidden bg-gray-400">
      Tjenare tjenare<!-- Column Content -->
    </div>

    <div class="w-1/4 p-5 my-5 overflow-hidden bg-gray-100">
      Tjenare tjenare<!-- Column Content -->
    </div>
  </div>
</template>

<script setup lang="ts">
import Toggle from "@/components/utils/Toggle.vue";
import DoubleLabelToggle from "@/components/utils/DoubleLabelToggle.vue";

</script>
