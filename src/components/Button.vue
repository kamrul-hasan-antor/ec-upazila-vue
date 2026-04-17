<script setup>
defineProps({
  label: { type: String, default: "Button" },
  type: { type: String, default: "button" },
  variant: { type: String, default: "primary" },
  disabled: { type: Boolean, default: false },
});

defineEmits(["click"]);
</script>

<template>
  <button
    :type="type"
    :disabled="disabled"
    :class="[
      'px-5 py-3 rounded font-semibold transition-colors duration-200 cursor-pointer',
      variant === 'primary' && 'bg-[#00814E] text-white hover:bg-[#006b40]',
      variant === 'secondary' && 'bg-[#F40224] text-white hover:bg-[#c40120]',
      variant === 'outline' &&
        'border border-[#00814E] text-[#00814E] hover:bg-[#00814E] hover:text-white',
      disabled && 'opacity-50 cursor-not-allowed',
    ]"
    @click="$emit('click')"
  >
    <span class="flex items-center justify-center gap-2">
      <slot>{{ label }}</slot>
    </span>
  </button>
</template>
