<template>
  <div class="container mt-5">
    <h1 class="mb-4">Enregistrement des Ventes</h1>
    <FormulaireVente @vente-ajoutee="ajouterVente" />
    <hr class="my-4">
    <TableauVentes :ventes="ventes" />
  </div>
</template>

<script>
import FormulaireVente from './components/FormulaireVente.vue';
import TableauVentes from './components/TableauVentes.vue';

export default {
  name: 'App',
  components: {
    FormulaireVente,
    TableauVentes
  },
  data() {
    return {
      ventes: []
    };
  },
  methods: {
    ajouterVente(vente) {
      this.ventes.push(vente);
    }
  }
}
</script>

<style>
/* Ajoutez ici les styles globaux si nécessaire */
</style>
