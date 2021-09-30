<template>
  <div class="flex flex-col justify-between h-screen">
    <h1 class="p-2 is-size-3 has-text-centered has-text-weight-bold">
      This iteration: Vue 3/Vuex 4/ts/vite/Composition API
    </h1>
    <div v-if="loading">
      <h3 class="mt-4 has-text-centered">
        Loading...
      </h3>
    </div>
    <div v-else>
      <p class="mt-2 has-text-centered">
        Mash temp: {{ mashTemp }}
      </p>
      <p class="mt-2 has-text-centered">
        Boil temp: {{ boilTemp }}
      </p>
      <p class="mt-2 has-text-centered">
        NatsClientStatus: {{ natsClientStatus }}
      </p>
    </div>
    Active sensors:
    <li
      v-for="sensorClient in activeSensors"
      :key="sensorClient"
    >
      {{ sensorClient }}
    </li>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, onMounted } from "vue";
import { useStore } from "@/store";
import { StoreApi } from "@/store/api";
import { eventbus } from "@/eventbus";

export default defineComponent({
  components: {},
  setup() {
    const store = useStore();
    const storeApi = new StoreApi();
    const loading = computed(() => store.state.loading);
    const natsClientStatus = computed(() => storeApi.getNatsClientStatus());
    onMounted(() => {
      storeApi.fauxLoading();
    });
    const mashTemp = computed(() => storeApi.getSensorValue("mash_temp"));
    const boilTemp = computed(() => storeApi.getSensorValue("boil_temp"));
    const activeSensors = computed(() => Array.from(storeApi.sensorClients()));
    return { loading, mashTemp, boilTemp, natsClientStatus, activeSensors };
  },
});
</script>
