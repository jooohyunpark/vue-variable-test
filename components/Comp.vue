<template>
  <div>
    <div>child - props data.a {{ data.a }} - {{ Math.random() }}</div>
    <!-- <div>child - props data.b {{ data.b }} - {{ Math.random() }}</div> -->
    <!-- <div>child - props data.c {{ data.c }} - {{ Math.random() }}</div> -->
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default: () => {},
    },
  },
};
</script>
