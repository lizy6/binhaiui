<template>
  <button
    class="lime-button"
    :class="{ [`lime-button-${type}`]: true }"
    type="button"
  >
    <slot></slot>
  </button>
</template>

<script>
import { oneOf } from "../../utils/assist";

export default {
  name: "Button",
  props: {
    type: {
      validator(value) {
        return oneOf(value, [
          "default",
          "primary",
          "info",
          "success",
          "warning",
          "error",
          "danger"
        ]);
      },
      type: String,
      default: "default"
    }
  }
};
</script>
