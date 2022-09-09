<template>
  <ul>
    <li :class="{ active: activeButton === 'poor' }">
      <butoon type="button" @click="activate('poor')">Poor</butoon>
    </li>
    <li :class="{ active: activeButton === 'average' }">
      <button type="button" @click="activate('average')">Average</button>
    </li>
    <li :class="{ active: activeButton === 'great' }">
      <button type="button" @click="activate('great')">Great</button>
    </li>
  </ul>
</template>
<script>
export default {
  //   data() {
  //     return {
  //       activeButton: this.modelValue,
  //     };
  //   },
  computed: {
    activeButton() {
      return this.modelValue;
    },
  },
  props: ['modelValue'],
  emits: ['updates:modelValue'],
  methods: {
    activate(option) {
      this.activeButton = option;
      this.$emit('updates:modelValue', option);
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}
li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-content: center;
}
button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>
