<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="testCepAdd(2, 3)">5 :-)</button>
    <button @click="testCepAddWithAlert(2, 5)">alert :-)</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods : {
    testCepAdd (num1: number, num2: number) {
      (window as any).__adobe_cep__. evalScript(`${num1}+${num2}`, console.log);
    },
    testCepAddWithAlert (num1: number, num2: number) {
      (window as any).__adobe_cep__. evalScript(`app.activeDocument.name`, console.log);
      (window as any).__adobe_cep__. evalScript(`alert(123)`, console.log);
    },
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
.hello
   color:red
h3
  margin 40px 0 0

ul
  list-style-type none
  padding 0

li
  display inline-block
  margin 0 10px

a
  color #0f0
</style>
