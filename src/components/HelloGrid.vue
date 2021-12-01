<template>
  <div class="grid-stack"/>
</template>

<script lang="ts">
import Vue from 'vue';
let cep = (window as any).__adobe_cep__;
let evalScript = cep.evalScript;
import 'gridstack/dist/gridstack.min.css';
import { GridStack } from 'gridstack';
// THEN to get HTML5 drag&drop
import 'gridstack/dist/h5/gridstack-dd-native';

export default Vue.extend({
  name: 'HelloGrid',
  props: {
    msg: String,
  },
  methods: {
    testCepAdd(num1: number, num2: number) {
      evalScript(`${num1}+${num2}`, console.log);
    },
    testCepAddWithAlert(num1: number, num2: number) {
      evalScript(`app.activeDocument.name`, console.log);
      evalScript(`alert(123)`, console.log);
    },
  },
     mounted: function() {
      const serializedData = [
        { x: 0, y: 0, w: 2, h: 2, content: 'item 1' },
        { x: 2, y: 3, w: 3, content: 'item 2' },
        { x: 1, y: 3, content: 'item 3'},
      ];
      let grid = GridStack.init();
      grid.load(serializedData);
      // GridStack.init();
      // grid.addWidget({w: 2, content: 'item 1'});
  },
 
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

.grid-stack
  color #00f
  
.1
  width 100px
  background-color red
  
.2
  width 150px
  background-color yellow
.grid-stack-item
  width 75px
  height 20px
  background-color #0f0
</style>
