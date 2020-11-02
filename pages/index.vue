<template>
  <div class="container">
    <div>data.a {{ data.a }} - {{ Math.random() }}</div>
    <div>data.b {{ data.b }} - {{ Math.random() }}</div>
    <div>data.c {{ data.c }} - {{ Math.random() }}</div>
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
      this.$set(this.data, "c", 0);
    },
    objectAssignC() {
      this.data = Object.assign({}, this.data, {
        c: 0,
      });
    },
    assignUnused() {
      this.unused = Math.random();
      console.log("variable updated but not used: ", this.unused);
    },
  },
};
</script>
