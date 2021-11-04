<template>
  <input type="checkbox" v-model="value" />
</template>

<script lang="ts">
import { defineComponent, inject, ref, watch } from 'vue'

export default defineComponent({
  name: 'ParCheckbox',
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const values: Record<string, string> = inject('values', {});
    const updateValue: any = inject('updateValue');
    const value = ref(values[props.id])

    watch(value, (newValue) => {
      updateValue(props.id, newValue)
    })

    return {
      value
    }
  }
});
</script>