<template>
  <div>
    <h2 class="mb-3">Ventes Enregistrées</h2>
    <table class="table">
      <thead>
        <tr>
          <th>Référence</th>
          <th>Désignation</th>
          <th>Quantité vendue</th>
          <th>Prix de vente</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(vente, index) in ventes" :key="index">
          <td>{{ vente.reference }}</td>
          <td>{{ vente.designation }}</td>
          <td>{{ vente.quantite }}</td>
          <td>{{ vente.prix }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'TableauVentes',
  props: {
    ventes: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
/* Ajoutez ici les styles spécifiques au composant TableauVentes.vue si nécessaire */
</style>
