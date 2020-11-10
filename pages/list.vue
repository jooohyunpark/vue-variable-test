<template>
  <div class="container">
    <div v-for="(item, i) in items" :key="i">
      {{ item.text }} {{ new Date() }}
    </div>

    <button @click="click">click</button>
    <button @click="click2">click2</button>

    <List :item="item" v-for="(item, i) in items" :key="i" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 0, text: "zero" },
        { id: 1, text: "one" },
        { id: 2, text: "two" },
      ],
    };
  },
  methods: {
    click() {
      this.items = [
        { id: 0, text: "zero" },
        { id: 1, text: "one---" },
        { id: 2, text: "two" },
      ];
    },
    click2() {
      this.$set(this.items, 1, { id: 1, text: "one---" });
    },
  },
};
</script>
