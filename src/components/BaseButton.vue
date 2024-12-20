<template>
  <button class="neo-btn neo-btn--red uppercase" v-on:click="onClick">
    {{ label }}
  </button>
</template>

<script lang="js">
export default {
  name: 'BaseButton',
  props: ['label', 'onClick'],
}
</script>
