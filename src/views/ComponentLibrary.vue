<template>
  <div class="flex flex-wrap -mx-5 overflow-hidden">
    <div class="w-1/2 px-5 my-5 overflow-hidden bg-gray-400">
      Tjenare tjenare<!-- Column Content -->
    </div>

    <div class="w-1/2 px-5 my-5 overflow-hidden bg-gray-100">
      Tjenare tjenare<!-- Column Content -->
    </div>

    <div class="w-1/2 px-5 my-5 overflow-hidden bg-gray-400">
      Tjenare tjenare<!-- Column Content -->
    </div>

    <div class="w-1/2 px-5 my-5 overflow-hidden bg-gray-100">
      <button @click="openModal()">
        Open modal
      </button>
      {{ modalStatus }}
      <Modal :is-open="modalStatus" />
    </div>
  </div>
</template>

<script setup lang="ts">
import Modal from "@/components/utils/Modal.vue";
import { useToggle } from "@vueuse/core";

const [modalStatus, openModal] = useToggle();
</script>
