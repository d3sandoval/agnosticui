<template>
  <li :class="classes">
    <slot />
  </li>
</template>

<script>
export default {
  name: "AgHeaderNavItem",
  props: {
    css: {
      type: String,
      default: "",
    },
  },
  computed: {
    classes() {
      return {
        [this.$style["header-nav-item"]]: true,
        [`${this.css}`]: !!this.css,
      };
    },
  },
};
</script>

<style module>
.header-nav-item {
  display: inline-block;
}

.header-nav-item:not(:last-child) {
  margin-inline-end: initial;
  margin-block-end: var(--fluid-8);
}

.header-nav-item a {
  color: var(--agnostic-header-color, var(--agnostic-font-color));
}

@media (min-width: 960px) {
  .header-nav-item:not(:last-child) {
    margin-inline-end: var(--agnostic-header-nav-spacing, var(--fluid-32));
    margin-block-end: initial;
  }
}

</style>
