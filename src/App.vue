<template>
<section>
<Cabecalho :valor="titulo"/>
  <div class="container">
    <AdicionarTarefa @adicionarTarefa="adicionarTarefa"/>

<ListarTarefas :tarefas="tarefas"/>

  
  <em>Altere aqui o titulo da sua lista de tarefas</em>
  <EntradaDeDados v-model="titulo" type="text"/>
  

  </div>
  <Rodape />
  </section>
</template>

<script>
import Cabecalho from "@/components/Cabecalho";
import Rodape from "@/components/Rodape";
import ListarTarefas from "@/components/ListarTarefas";
import AdicionarTarefa from "@/components/AdicionarTarefa";
import EntradaDeDados from "@/components/templates/EntradaDeDados";


export default {
  name: 'App',
  components: {Cabecalho, Rodape, ListarTarefas, AdicionarTarefa, EntradaDeDados},
  data() {
    return {

      titulo: "minha lista de tarefas",
      tarefas: [
        { titulo:"Estudar", checked: false},
        { titulo:"Ler", checked: true},
      ],
    };
  },
  methods: {
    adicionarTarefa(novaTarefa) {
      this.tarefas.push({
        titulo: novaTarefa,
        checked: false
      });
    },
  },
};
</script>

<style>

</style>
