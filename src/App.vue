<template>
  <div id="app">
    <h1 class="text-center print:hidden">Neofonie Badge Generator</h1>
    <OverVue />
  </div>
</template>

<script lang="js">
import OverVue from './components/Over.vue'

export default {
  name: 'app',
  components: {
    OverVue,
  },
}
</script>

<style lang="less">
@media print {
  .overvue .docsize {
    border: 0 !important;
    height: auto !important;
    margin: 0 !important;
  }
}

.fas {
  cursor: pointer;

  &:hover {
    color: var(--clr-red) !important;
    text-shadow: 0 0 4px rgba(0, 0, 0, 0.25);
  }
}
</style>
