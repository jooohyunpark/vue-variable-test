<template>
  <div class="container">
    <div>data.a {{ data.a }} - {{ Math.random() }}</div>
    <div>data.b {{ data.b }} - {{ Math.random() }}</div>
    <div>data.c {{ data.c }} - {{ Math.random() }}</div>
    <div v-for="(item, i) in array" :key="i">
      array {{ item }} - {{ Math.random() }}
    </div>

    <Comp :data="data" />

    <br />
    <br />
    <button @click="addA">a++</button>
    <button @click="addB">b++</button>
    <button @click="addC">c++</button>
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
    <button @click="defineObject">define object directly</button>
    <br />
    <br />
    <button @click="pushArray">push to array</button>
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
      array: [],
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
    addC() {
      this.data.c += 1;
    },
    assignC() {
      this.data.c = Math.random();
      console.log(this.data);
    },
    setC() {
      this.$set(this.data, "c", 0);
    },
    objectAssignC() {
      this.data = Object.assign({}, this.data, {
        c: 0,
      });
    },
    defineObject() {
      this.data = { a: 1, b: 1 };
    },
    assignUnused() {
      this.unused = Math.random();
      console.log("variable updated but not used: ", this.unused);
    },
    pushArray() {
      this.array.push(Math.random());
    },
  },
};
</script>
