<template>
  <div class="container">
    <div>data.a {{ data.a }} - {{ Math.random() }}</div>
    <div>data.b {{ data.b }} - {{ Math.random() }}</div>
    <div>data.c {{ data.c }} - {{ Math.random() }}</div>
    <div>empty.a {{ empty.a }} - {{ Math.random() }}</div>

    <Comp :data="data" />

    <br />
    <br />
    <button @click="addA">a++</button>
    <button @click="addB">b++</button>
    <br />
    <br />
    <button @click="assignC">assign data.c directly</button>
    <button @click="setC">set data.c</button>
    <button @click="objectAssignC">object.assign data</button>
    <br />
    <br />
    <button @click="assignUnused">assign unused</button>
    <br />
    <br />
    <button @click="setEmpty">set empty object</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: {
        a: 0,
        b: 0,
      },
      empty: {},
      unused: null,
    };
  },
  methods: {
    addA() {
      this.data.a += 1;
    },
    addB() {
      this.data.b += 1;
    },
    assignC() {
      this.data.c = Math.random();
    },
    setC() {
      this.$set(this.data, "c", Math.random());
    },
    objectAssignC() {
      this.data = Object.assign({}, this.data, {
        c: 0,
      });
    },
    setEmpty() {
      this.data = { a: 1, b: 1 };
      // this.$set(this.empty, "c", Math.random());
    },
    assignUnused() {
      this.unused = Math.random();
      console.log("variable updated but not used: ", this.unused);
    },
  },
};
</script>
