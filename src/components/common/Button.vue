<template>
  <button
    @click="e => onClick && onClick(e)"
    type="button"
    :class="{ secondary: isSecondary }"
  >
    {{text}}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: ['text', 'onClick', 'isSecondary'],
};
</script>

<style scoped>
@import '../../variables';

button {
  font-family: var(--main-font);
  background-color: var(--white);
  color: var(--main-color);
  text-transform: uppercase;
  border-radius: 5px;
  border-width: 0;
  padding: 10px;
  box-shadow: 0px 0px 3px 2px rgba(0, 0, 0, 0.25);
  cursor: pointer;

  &:hover {
    transform: translateY(2px);
  }

  &:active {
    background-color: var(--main-color);
    color: var(--white);
  }

  &:active,
  &:hover,
  &:focus {
    outline: none;
  }

  &:disabled {
    pointer-events: none;
    background: var(--light-grey);
    color: var(--white);
  }

  &.secondary {
    background-color: var(--main-color);
    color: var(--white);

    &:active {
      background-color: var(--white);
      color: var(--main-color);
    }
  }
}
</style>
