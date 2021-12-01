<script>
function allowDrop(ev) {
  ev.preventDefault();
}

function drag(ev) {
  ev.dataTransfer.setData('text', ev.target.id);
}

function drop(ev) {
  ev.preventDefault();
  var data = ev.dataTransfer.getData('text');
  ev.target.appendChild(document.getElementById(data));
}
</script>

<template>
  <div id="app">
    <hello></hello>
    <div
      id="div1"
      @drop="drop(event)"
      @dragover="allowDrop(event)"
      style="background: green"
    >
      drag to here
    </div>

    <div
      id="drag1"
      draggable="true"
      @dragstart="drag(event)"
      style="background: red"
    >
      drag me 💥💨
    </div>
  </div>
</template>

<script>
import Hello from './components/Hello';
export default {
  name: 'app',
  components: {
    Hello,
  },
  methods: {
    allowDrop: function(ev) {
      ev.preventDefault();
    },

    drag: function(ev) {
      ev.dataTransfer.setData('text', ev.target.id);
    },

    drop: function(ev) {
      ev.preventDefault();
      var data = ev.dataTransfer.getData('text');
      ev.target.appendChild(document.getElementById(data));
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2adf2a;
}
#app .logo {
  text-align: center;
}
</style>
