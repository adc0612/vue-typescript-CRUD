<template>
  <div>
    <label for="todo-input"></label>
    <input type="text" name="" id="todo-input" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">add</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  props: {
    item: {
      type: String,
      required: true,
    },
  },
  methods: {
    addTodo() {
      this.$emit('add');
    },
    handleInput(event: InputEvent) {
      const eventTarget = event.target as HTMLInputElement;
      this.$emit('input', eventTarget.value);
    },
  },
});
</script>

<style></style>
