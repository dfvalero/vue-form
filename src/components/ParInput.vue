<template>
  <input type="text" :value="value" @input="onInput" />
</template>

<script lang="ts">
import { defineComponent, inject } from 'vue';

export default defineComponent({
  name: 'ParInput',
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const values: Record<string, string> = inject('values', {});
    const updateValue: any = inject('updateValue');
    const value = values[props.id]

    const onInput = (e: any) => {
      updateValue(props.id, e.target.value)
    }

    return {
      value,
      onInput
    }
  }
});
</script>