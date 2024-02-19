<script setup>
import { ref } from 'vue';
const operations = ref({
  type: 'crédit',
  description: 'remboursement frais médicaux',
  montant: '25',
},
{
  type: 'débit',
  description: 'achat chaussures',
  montant: '75'
  
});
;

const application = {
  data() {
    return {
      operations: window.operations,
      newOperation: {

      }
    }
  }
}
methods: {
    addOperation: function()
}
</script>

<template>
  <header>
<div id="logo">logo</div>
  <h1>WALLET WIZARD</h1>  
  </header>
  <main>
<div class="container main" id="app">
  <table class="table">
    <thead>
      <tr>
        <th scope="col">Type d'opération</th>
        <th scope="col">Montant</th>
        <th scope="col">Description</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(operation) in operations">
        <td>{{ operation.type }}</td>
        <td>{{ operation.description }}</td>
        <td>{{ operation.montant }}</td>
      </tr>
    </tbody>
  </table>
</div>

<form>
  <div class="row">
    <div class="col">
    Crédit
      <input type="checkbox" name="creditCheckbox" class="form-control" id="creditCheckbox">
    </div>
    <div class="col">
      Débit
      <input type="checkbox" name="debitCheckbox" class="form-control" id="debitCheckbox">
    </div>
      <br>
    <div class="col">
    Description :
      <input type="text" name="description" class="form-control" id="descriptionOperation" v-model="newOperation.description">
    </div>
      <br>
    <div class="col">
    Montant :
      <input type="text" name="montant" class="form-control" id="montantOperation" v-model="newOperation.montant">
    </div>
      <br>
    <button type="submit" id="submit">AJOUTER</button>

  </main>

    <button type="submit" id="total">TOTAL</button>
    <input type="text">
  </div>
</form>
</template>

<style scoped>

</style>
