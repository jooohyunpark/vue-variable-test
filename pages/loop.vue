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
        // { id: 3, text: "three" },
        // { id: 4, text: "four" },
        // { id: 5, text: "five" },
        // { id: 6, text: "six" },
        // { id: 7, text: "seven" },
        // { id: 8, text: "eight" },
        // { id: 9, text: "nine" },
        // { id: 10, text: "ten" },
      ],
    };
  },
  mounted() {
    // minimizing property lookups
    // up to 25% faster
    for (var i = 0, len = this.items.length; i < len; i++) {
      console.log(i);
    }

    console.log("-----");

    // minimizing property lookups and reversing
    // up to 50–60% faster
    for (var i = this.items.length; i--; ) {
      console.log(i);
    }

    console.log("-----");

    //credit: Jeff Greenberg
    var iterations = Math.floor(this.items.length / 8),
      startAt = this.items.length % 8,
      i = 0;

    do {
      console.log("iteration: ", iterations);
      switch (startAt) {
        case 0:
          console.log(i);
          i++;
        case 7:
          console.log(i);
          i++;
        case 6:
          console.log(i);
          i++;
        case 5:
          console.log(i);
          i++;
        case 4:
          console.log(i);
          i++;
        case 3:
          console.log(i);
          i++;
        case 2:
          console.log(i);
          i++;
        case 1:
          console.log(i);
          i++;
      }
      startAt = 0;
      console.log("iteration: ", iterations);
    } while (iterations--);
  },
  methods: {},
};
</script>
