<template>
  <button
    @click="onClick"
    class="text-indigo-600 hover:text-indigo-900 text-sm font-medium"
  >
    <slot></slot>
  </button>
</template>

<script setup>
const emit = defineEmits(['click']);

const onClick = () => {
  emit('click');
};
</script>
