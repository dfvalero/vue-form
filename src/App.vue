<template>
  <par-form :values="values">
    <div class="super-nested-section">
      <div>
        <par-input id="first" />
      </div>
    </div>
    <div class="super-nested-section">
      <div>
        <par-input id="second" />
      </div>
    </div>
    <div class="super-nested-section">
      <div>
        <par-checkbox id="third" />
      </div>
    </div>
    <button type="submit">Submit</button>
  </par-form>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ParForm from './components/ParForm.vue';
import ParInput from './components/ParInput.vue';
import ParCheckbox from './components/ParCheckbox.vue';

export default defineComponent({
  name: 'App',
  components: {
    ParForm,
    ParInput,
    ParCheckbox
  },
  data() {
    return {
      values: {
        first: '1',
        second: '',
        third: true
      }
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
