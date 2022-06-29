<template>
  <v-btn
    :class="{ [`text-${textColour}`]: textColour }"
    :color="colour"
    :size="isMobile ? 'small' : 'default'"
    :density="density"
    :variant="variant"
  >
    {{ text }}
  </v-btn>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import { isMobile } from "@/utility/width";

export default defineComponent({
  name: "Button",
  props: {
    text: {
      type: String,
      default: "",
    },
    colour: {
      type: String,
      default: undefined,
    },
    textColour: {
      type: String,
      default: "",
    },
    density: {
      type: String as PropType<"default" | "compact" | "comfortable">,
      default: "default",
    },
    variant: {
      type: String as PropType<
        "flat" | "text" | "elevated" | "tonal" | "outlined" | "plain"
      >,
      default: "elevated",
    },
  },
  setup() {
    return {
      isMobile,
    };
  },
});
</script>

<style lang="scss" scoped></style>
