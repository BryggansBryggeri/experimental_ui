<template>
  <SwitchGroup>
    <div class="flex items-center space-x-2">
      <SwitchLabel
        class=""
        :class="enabled ? 'cursor-pointer' : 'cursor-not-allowed'"
        :passive="!enabled"
      >
        {{ leftLabel }}
      </SwitchLabel>
      <Switch
        v-model="enabled"
        :class="enabled ? 'bg-blue-600' : 'bg-gray-200'"
        class="
          relative
          inline-flex
          items-center
          h-6
          transition-colors
          rounded-full
          w-11
          focus:outline-none
          focus:ring-2
          focus:ring-offset-2
          focus:ring-indigo-500
        "
      >
        <span
          :class="enabled ? 'translate-x-6' : 'translate-x-1'"
          class="
            inline-block
            w-4
            h-4
            transition-transform
            transform
            bg-white
            rounded-full
          "
        />
      </Switch>
      <SwitchLabel
        class=""
        :class="enabled ? 'cursor-not-allowed' : 'cursor-pointer'"
        :passive="enabled"
      >
        {{ rightLabel }}
      </SwitchLabel>
    </div>
  </SwitchGroup>
</template>

<script lang="ts">
import { ref } from "vue";
import { Switch, SwitchGroup, SwitchLabel } from "@headlessui/vue";

export default {
  components: { Switch, SwitchGroup, SwitchLabel },
  props: {
    leftLabel: {
      type: String,
      required: true,
    },
    rightLabel: {
      type: String,
      required: true,
    },
  },

  setup() {
    const enabled = ref(false);

    return { enabled };
  },
};
</script>
