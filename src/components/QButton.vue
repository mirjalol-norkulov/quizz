<template>
  <component :is="component">
    <slot />
  </component>
</template>

<script>
export default {
  name: "QButton",
  props: {
    href: {
      type: String,
    },
    to: {
      type: [Object, String],
    },
  },
  computed: {
    component() {
      if (this.href) {
        return "a";
      }
      if (this.to) {
        return "router-link";
      }

      return "button";
    },
  },
};
</script>
