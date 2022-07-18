<template>
  <div>
    <input v-model="modelValue.name" />
    <input type="number" v-model="modelValue.quantity" />
    <input type="number" v-model="modelValue.price" />
    <input v-model="sum" disabled />
    <hr />
  </div>
</template>

<script>
export default {
  name: 'FormRow',
  props: ['modelValue'],
  computed: {
    sum() {
      return this.modelValue.quantity * this.modelValue.price;
    },
  },
};
</script>

<style>
input {
  width: 100px;
  margin: 5px;
}
</style>
