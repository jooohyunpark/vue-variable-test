<template>
  <div></div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 0, text: "zero" },
        { id: 1, text: "one" },
        { id: 2, text: "two" },
        { id: 3, text: "three" },
        { id: 4, text: "four" },
        { id: 5, text: "five" },
      ],
    };
  },
  mounted() {
    // minimizing property lookups
    // around 25% faster
    for (var i = 0, len = this.items.length; i < len; i++) {
      console.log(i);
    }

    console.log("-----");

    // minimizing property lookups and reversing
    // around 50–60% faster
    for (var i = this.items.length; i--; ) {
      console.log(i);
    }
  },
};
</script>
