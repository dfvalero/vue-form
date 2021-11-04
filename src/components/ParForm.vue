<template>
  <form @submit.prevent="onSubmit">
    <slot></slot>
  </form>
</template>

<script lang="ts">
import { defineComponent, provide, reactive } from 'vue';

export default defineComponent({
  name: 'ParForm',
  props: {
    values: {
      type: Object,
      default: () => ({}),
    },
  },
  setup(props) {
    const state = reactive({
      values: props.values,
    });

    const updateValue = (id: string, value: string) => {
      state.values[id] = value
    }

    provide('values', state.values)
    provide('updateValue', updateValue)

    const onSubmit = () => {
      alert(JSON.stringify(state.values, null, 4));
    }

    return {
      onSubmit
    }
  },
});
</script>