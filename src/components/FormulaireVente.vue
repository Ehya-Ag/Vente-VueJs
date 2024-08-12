<template>
  <form @submit.prevent="soumettreFormulaire">
    <div class="mb-3">
      <label for="reference" class="form-label">Référence :</label>
      <input type="text" class="form-control" id="reference" v-model="vente.reference" required>
    </div>
    <div class="mb-3">
      <label for="designation" class="form-label">Désignation :</label>
      <input type="text" class="form-control" id="designation" v-model="vente.designation" required>
    </div>
    <div class="mb-3">
      <label for="quantite" class="form-label">Quantité vendue :</label>
      <input type="number" class="form-control" id="quantite" v-model.number="vente.quantite" required>
    </div>
    <div class="mb-3">
      <label for="prix" class="form-label">Prix de vente :</label>
      <input type="number" class="form-control" id="prix" v-model.number="vente.prix" required>
    </div>
    <button type="submit" class="btn btn-primary">Enregistrer la vente</button>
  </form>
</template>

<script>
export default {
  name: 'FormulaireVente',
  data() {
    return {
      vente: {
        reference: '',
        designation: '',
        quantite: null,
        prix: null
      }
    };
  },
  methods: {
    soumettreFormulaire() {
     
      if (!this.vente.reference || !this.vente.designation || !this.vente.quantite || !this.vente.prix) {
        alert('Veuillez remplir tous les champs.');
        return;
      }
      
      if (this.vente.quantite <= 0 || this.vente.prix <= 0) {
        alert('La quantité vendue et le prix de vente doivent être supérieurs à zéro.');
        return;
      }

      this.$emit('vente-ajoutee', { ...this.vente });

      this.vente = {
        reference: '',
        designation: '',
        quantite: null,
        prix: null
      };
    }
  }
}
</script>

<style scoped>
</style>
