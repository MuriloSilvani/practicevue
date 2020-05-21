<template>
  <div>
    <span>total: {{ contador }}</span>

    <button class="button" v-on:click="decrementar()">-</button>
    <button class="button" v-on:click="acrescentar()">+</button>

    <section>
      <input v-model="input" />
      <!-- <p>{{ input }}</p> -->

      <button class="button" @click="alertar()" v-if="input">Entrar</button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contador: 0,
      input: undefined,
      nome: "joao"
    };
  },
  methods: {
    acrescentar() {
      this.contador++;
    },
    decrementar() {
      this.contador--;
    },
    alertar() {
      alert(this.input + " Legal");
    }
  },
  beforeUpdate() {
    console.log("Atualizando");
  },
  updated() {
    console.log(" contador: " + this.contador + ", atualizado");
  },
  created() {
    // setInterval(() => {
    // this.contador++;
    // }, 1500);
  },
  destroyed() {
    console.log(this);
  }
};
</script>

<style scoped>
.button {
  background: rgba(240, 50, 50, 1);
  border: none;
  border-radius: 5px;
  color: #fff;
  padding: 10px 25px;
  margin: 5px 10px;
  font-weight: bold;
}
</style>