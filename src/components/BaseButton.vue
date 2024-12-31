<template>
  <button class="neo-btn neo-btn--red uppercase" v-on:click="onClick">
    {{ label }}
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: ['label', 'onClick'],
}
</script>
