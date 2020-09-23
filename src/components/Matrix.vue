<template>
  <div
    class="matrix"
    :style="{
      height: `${size}px`,
      width: `${size}px`,
    }"
  >
    <div
      class="matrix__item"
      :class="{ 'active': modelValue[i-1] === 1}"
      v-for="i in 25"
      :key="i"
      @click="clickItem(i-1)"
    ></div>
  </div>
</template>

<script>
  import { toRefs } from 'vue';

  export default {
    name: "Matrix",
    props: {
      size: {
        type: Number,
        default: 250
      },
      modelValue: {
        type: Array,
        required: true
      },
    },
    setup (props, { emit }) {
      const { modelValue: array } = toRefs(props);
      const clickItem = (i) => {
        array.value[i] = 1 - array.value[i];
        emit('update:modelValue', array.value);
      };

      return {
        clickItem
      };
    }
  }
</script>

<style lang="sass">
.matrix
  display: flex
  flex-wrap: wrap
  border: 1px solid #2c3e50
  box-sizing: border-box
  &__item
    box-sizing: border-box
    border: 1px solid #2c3e50
    width: 20%
    height: 20%
    cursor: pointer
    &.active
      background-color: #2c3e50
</style>