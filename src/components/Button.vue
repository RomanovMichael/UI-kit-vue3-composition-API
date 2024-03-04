<script setup>
const props = defineProps({
  label: {
    type: String,
    default: "Button",
  },
  color: {
    type: String,
    default: "primary",
  },
  disabled: {
    type: Boolean,
    required: false,
  },
  rounded: {
    type: Boolean,
    required: false,
  },
  outlined: {
    type: Boolean,
    required: false,
  },
  size: {
    type: String,
    default: "normal",
  },
});

const emit = defineEmits(["click"]);

const clickOnButton = () => {
  emit("click");
};
</script>

<template>
  <button
    :class="[
      'btn',
      `btn--${color}`,
      { 'btn--rounded': rounded },
      { 'btn--outlined': outlined },
      { 'btn--large': size === 'large' },
    ]"
    @click="clickOnButton"
    :disabled="disabled"
  >
    {{ label }}
  </button>
</template>

<style lang="scss" scoped>
.btn {
  margin-right: 10px;
  margin-bottom: 10px;
  padding: 0 20px;
  height: 40px;
  color: #fff;
  border-radius: 7px;
  border: none;
  cursor: pointer;
  font-size: 15px;
  transition: 0.2s;

  &--primary {
    background: var(--primary);
    border: 1px solid var(--primary);
    &:enabled:hover {
      background: var(--primary-hover);
    }
  }
  &--second {
    background: var(--second);
    border: 1px solid var(--second);
    &:enabled:hover {
      background: var(--second-hover);
    }
  }
  &--success {
    background: var(--success);
    border: 1px solid var(--success);
    &:enabled:hover {
      background: var(--success-hover);
    }
  }
  &--info {
    background: var(--info);
    border: 1px solid var(--info);
    &:enabled:hover {
      background: var(--info-hover);
    }
  }
  &--warning {
    background: var(--warning);
    border: 1px solid var(--warning);
    &:enabled:hover {
      background: var(--warning-hover);
    }
  }
  &--danger {
    background: var(--danger);
    border: 1px solid var(--danger);
    &:enabled:hover {
      background: var(--danger-hover);
    }
  }
  &:disabled {
    opacity: 0.6;
    cursor: default;
  }
  &--rounded {
    border-radius: 15px;
  }
  &--outlined {
    background: transparent;
    color: #000;
    &:hover {
      color: #fff;
    }
  }
  &--icon {
    padding: 0;
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
  &--large {
    height: 48px;
    padding: 0 30px;
  }
}
</style>