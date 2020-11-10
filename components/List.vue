<template>
  <div>{{ item.text }} {{ new Date() }}</div>
</template>

<script>
export default {
  props: {
    item: {
      default: () => {},
      type: Object,
    },
  },
};
</script>
