<template>
  <label :for="id" class="neo-checkbox checkbox__container">
    {{ label }}
    <input :id="id" type="checkbox" :checked="modelValue" @change="onChange" />
    <span class="checkmark"></span>
  </label>
</template>

<script>
export default {
  name: 'BaseCheckbox',

  props: {
    label: {
      type: String,
      required: true,
    },
    modelValue: {
      type: Boolean,
      required: true,
    },
    id: {
      type: String,
      required: false,
      default: () => `checkbox-${Math.random().toString(36).substr(2, 9)}`, // Generates a unique ID if none is provided
    },
  },

  emits: ['update:modelValue'],

  methods: {
    onChange(event) {
      this.$emit('update:modelValue', event.target.checked)
    },
  },
}
</script>

<style lang="less">
.checkbox__container {
  @apply flex items-center select-none cursor-pointer;

  &:hover .checkmark {
    @apply bg-gray-500;
  }

  input {
    @apply absolute h-0 w-0 opacity-0 cursor-pointer;

    &:checked ~ .checkmark {
      @apply bg-neo-red;

      &:after {
        @apply block;
      }
    }
  }

  .checkmark {
    @apply relative h-6 w-6 bg-gray-300 ml-1;

    &:after {
      @apply absolute hidden border-white;
      content: '';
      left: 9px;
      top: 5px;
      width: 5px;
      height: 10px;
      border-width: 0 3px 3px 0;
      transform: rotate(45deg);
    }
  }
}
</style>
