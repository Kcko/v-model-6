<template>
  <div id="app">
    Celková cena je: {{ totalPrice }}
    <br />
    <button @click="addNewRow">add new row</button>
    <FormRow
      v-for="(item, index) in items"
      :key="item.name"
      v-model="items[index]"
    />
  </div>
</template>

<script>
import FormRow from './components/FormRow';

export default {
  name: 'App',
  components: {
    FormRow,
  },
  data() {
    return {
      items: [
        {
          name: 'A',
          quantity: 1,
          price: 10,
        },
        {
          name: 'B',
          quantity: 2,
          price: 20,
        },
      ],
    };
  },
  computed: {
    totalPrice() {
      let total = 0;
      this.items.forEach((item) => {
        total += item.price * item.quantity;
      });

      return total;
    },
  },
  methods: {
    addNewRow() {
      this.items.push({
        name: null,
        quantity: 0,
        price: 0,
      });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
