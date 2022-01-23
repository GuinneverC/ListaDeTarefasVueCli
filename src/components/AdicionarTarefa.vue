<template>
  <div class="input-group">
     <!-- <input @keyup.enter="adicionarTarefa" type="text" v-model="novaTarefa">-->
      <!--  <EntradaDeDados :value="novaTarefa" @input="associarValor"/>   -->
      <entrada-de-dados @salvar="adicionarTarefa" v-model="novaTarefa" />
      <span class="input-group-btn">
        <button @click="adicionarTarefa" class="btn btn-primary">Adicionar</button>
      </span>
  </div>
</template>

<script>
import EntradaDeDados from "@/components/templates/EntradaDeDados";

export default {
    components: {EntradaDeDados,},

data() {
    return {
        novaTarefa: "",
    };
},
methods: {
    adicionarTarefa() {
        this.$emit('adicionarTarefa', this.novaTarefa);
        this.novaTarefa = "";
    },
   // associarValor(valor) {
   //     this.novaTarefa = valor;
   // },
},
};
</script>

<style>

</style>