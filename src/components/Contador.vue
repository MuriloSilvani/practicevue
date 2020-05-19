<template>
  <div>
    <span>total: {{ contador }}</span>

    <button v-on:click="decrementar()">-</button>
    <button v-on:clickcd="acrescentar()">+</button>

    <section>
      <input v-model="input" />
      <p>{{ input }}</p>

      <button v-if="input">Entrar</button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contador: 0,
      input: undefined
    };
  },
  methods: {
    acrescentar() {
      this.contador++;
    },
    decrementar() {
      this.contador--;
    }
  }
};
</script>

<style scoped>
</style>