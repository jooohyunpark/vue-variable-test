<template>
  <div class="container">
      <p id="para1">P1</p>
      <p id="para2">P2</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
 
    };
  },
 mounted() {
   
   
  function noClosure() {
    var cFoo = 900
    var cBaz = new Array(100)
    function closureFunc() {
        return cFoo
    }
    return closureFunc
}
var closure = noClosure()
closure()
// 900

console.log(closure())
console.dir(closure)


console.log("----------------")

function outer() {
    const potentiallyHugeArray = [];
    return function inner() {
        potentiallyHugeArray.push('Hello'); // function inner is closed over the potentiallyHugeArray variable
        console.log('Hello');
    };
};
const sayHello = outer(); // contains definition of the function inner

function repeat(fn, num) {
    for (let i = 0; i < num; i++){
        fn();
    }
}
repeat(sayHello, 10);

console.dir(sayHello)


console.log("----------------")


  },
};
</script>
