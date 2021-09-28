<template>
  <div class="container mx-auto mt-4">
    <p class="mt-2 has-text-centered">
      {{ id }}: {{ val }}
    </p>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent } from "vue";
import { StoreApi } from "@/store/api";

export default defineComponent({
  components: {},
  props: {
    id: { type: String, required: true },
  },
  setup(props) {
    const storeApi = new StoreApi();
    const val = computed(() => storeApi.getSensorValue(props.id));
    return { val };
  },
});
</script>
