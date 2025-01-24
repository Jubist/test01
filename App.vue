<template>
  <div id="app">
    <h1>Gestion de Factures</h1>
    
    <!-- Formulaire d'ajout de facture -->
    <div class="form-container">
      <h2>Ajouter une facture</h2>
      <form @submit.prevent="ajouterFacture">
        <div class="form-group">
          <label for="nom">Nom de la facture :</label>
          <input type="text" id="nom" v-model="facture.nom" required placeholder="Ex : Facture d'achat" />
        </div>
        
        <div class="form-group">
          <label for="date">Date d'émission :</label>
          <input type="date" id="date" v-model="facture.date" required />
        </div>
        
        <div class="form-group">
          <label for="montant">Montant :</label>
          <input type="number" id="montant" v-model="facture.montant" required min="0" placeholder="0.00" />
        </div>

        <button type="submit" class="btn-primary">Ajouter</button>
      </form>
    </div>

    <!-- Liste des factures -->
    <div class="facture-list">
      <h2>Liste des Factures</h2>
      <table>
        <thead>
          <tr>
            <th>Nom</th>
            <th>Date d'émission</th>
            <th>Montant</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(facture, index) in factures" :key="index">
            <td>{{ facture.nom }}</td>
            <td>{{ facture.date }}</td>
            <td>{{ facture.montant }}$</td>
            <td>
              <button @click="supprimerFacture(index)" class="btn-danger">Supprimer</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      facture: {
        nom: '',
        date: '',
        montant: 0
      },
      factures: []
    };
  },
  methods: {
    ajouterFacture() {
      if (this.facture.nom && this.facture.date && this.facture.montant > 0) {
        this.factures.push({ ...this.facture });
        // Réinitialiser les champs du formulaire
        this.facture.nom = '';
        this.facture.date = '';
        this.facture.montant = 0;
      }
    },
    
    supprimerFacture(index) {
      this.factures.splice(index, 1);
    }
  }
};
</script>

<style scoped>
/* Style global */
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f4f7fa;
  color: #333;
  padding: 20px;
  max-width: 900px;
  margin: 0 auto;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

h1, h2 {
  color: #2c3e50;
  font-weight: 600;
  text-align: center;
  margin-bottom: 30px;
}

/* Conteneur du formulaire */
.form-container {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
  margin-bottom: 30px;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  font-weight: 500;
  color: #666;
  margin-bottom: 5px;
}

.form-group input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 8px;
  font-size: 14px;
  transition: border-color 0.3s ease;
}

.form-group input:focus {
  border-color: #4CAF50;
  outline: none;
}

/* Boutons */
button {
  padding: 10px 15px;
  border: none;
  border-radius: 8px;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn-primary {
  background-color: #4CAF50;
  color: white;
}

.btn-primary:hover {
  background-color: #45a049;
}

.btn-danger {
  background-color: #e74c3c;
  color: white;
}

.btn-danger:hover {
  background-color: #c0392b;
}

/* Liste des factures */
.facture-list {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

th, td {
  padding: 12px 15px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

th {
  background-color: #f1f1f1;
  font-weight: 600;
}

tbody tr:hover {
  background-color: #f9f9f9;
}

tbody tr:last-child td {
  border-bottom: none;
}
</style>
