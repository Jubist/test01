# project1

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


Description
Ce projet est une application de gestion de factures développée avec Vue.js. Il permet aux utilisateurs d'ajouter, de visualiser et de supprimer des factures. Chaque facture comprend un nom, une date d'émission et un montant. L'application offre une interface moderne et réactive, avec des effets d'animation pour rendre l'expérience utilisateur agréable.

Fonctionnalités
•	Ajout de factures : Permet d'ajouter une nouvelle facture avec un nom, une date et un montant.
•	Suppression de factures : Permet de supprimer une facture de la liste.
•	Affichage dynamique : La liste des factures est mise à jour en temps réel sans besoin de recharger la page.
•	Interface moderne : Interface responsive avec un design simple et élégant, utilisant des transitions et des effets d'animation.

Prérequis
Avant de commencer, assurez-vous que vous avez les outils suivants installés sur votre machine :
•	Node.js : Utilisé pour exécuter JavaScript côté serveur et installer des dépendances.
•	npm : Le gestionnaire de paquets pour JavaScript, inclus avec Node.js.

Utilisation
Une fois l'application lancée dans votre navigateur, vous pouvez interagir avec elle de la manière suivante :
Ajouter une facture :
o	Dans le formulaire "Ajouter une facture", remplissez les champs : nom, date d'émission et montant.
o	Cliquez sur le bouton Ajouter pour ajouter la facture à la liste.
Voir les factures :
o	Les factures ajoutées apparaîtront dans un tableau sous le formulaire. Chaque ligne affiche le nom de la facture, sa date d'émission et son montant.
Supprimer une facture :
o	Pour supprimer une facture, cliquez sur le bouton Supprimer à côté de la facture dans le tableau. Cela supprimera la facture de la liste.

Exemple de facture :
•	Nom : Facture de Bastien
•	Date d'émission : 2024-11-10
•	Montant : 150$

Fichier principal App.vue
Le fichier App.vue contient le code de l'interface utilisateur et la logique du programme (ajout, suppression de factures). Il inclut aussi les styles CSS pour rendre l'interface moderne et interactive.

Contribution
Si vous souhaitez contribuer à ce projet, voici les étapes à suivre :
1.	Forkez ce repository.
2.	Créez une branche pour votre fonctionnalité (git checkout -b ma-fonctionnalité).
3.	Modifiez le code et effectuez vos changements.
4.	Testez vos modifications.
5.	Soumettez un pull request avec une description détaillée de vos changements.

Crédits
•	Vue.js : Le framework JavaScript utilisé pour la création de l'application.
•	CSS : Des styles modernes et interactifs sont utilisés pour améliorer l'interface utilisateur.


1. Vue d'ensemble de l'application
L'application de gestion de factures permet aux utilisateurs d'ajouter, de visualiser et de supprimer des factures. Chaque facture comprend un nom, une date d'émission et un montant. L'interface utilise Vue.js pour gérer les interactions et les mises à jour du DOM, tout en utilisant un style moderne et interactif grâce à des animations et des transitions.

2. Composants Vue.js
Composant App
Le composant principal de l'application est un seul fichier Vue qui contient à la fois le modèle, la logique et le style. Ce fichier gère la fonctionnalité complète de l'application.

Template : La structure HTML de l'interface, avec un formulaire pour ajouter des factures et une table pour les afficher.
Script : La logique Vue.js pour gérer l'ajout et la suppression de factures.
Style : Les styles CSS scoped sont appliqués à ce composant pour garantir une apparence moderne et interactive.

3. Propriétés du modèle de données

facture
Cet objet représente les informations d'une facture en cours de saisie dans le formulaire. Il est réinitialisé après l'ajout d'une nouvelle facture.

nom : Chaîne de caractères, nom de la facture.
date : Chaîne de caractères au format date, la date d'émission de la facture.
montant : Nombre, montant de la facture en dollars.

factures
Un tableau d'objets représentant toutes les factures ajoutées. Chaque objet facture contient un ID unique (id basé sur Date.now()), un nom, une date et un montant.

4. Méthodes Vue.js

Méthode ajouterFacture
Cette méthode est appelée lors de la soumission du formulaire. Elle permet d'ajouter une nouvelle facture à la liste des factures (factures). Avant d'ajouter la facture, elle vérifie que les champs nom, date et montant sont remplis correctement.

Actions :
Si les champs sont valides, la facture est ajoutée à la liste avec un identifiant unique généré par Date.now().
Les champs du formulaire sont réinitialisés après l'ajout de la facture.

Méthode supprimerFacture
Cette méthode permet de supprimer une facture de la liste factures. Elle est déclenchée par un clic sur le bouton "Supprimer" à côté de chaque facture dans la table.

Actions : 
La facture à l'index donné est supprimée du tableau factures à l'aide de la méthode splice.

5. Gestion des transitions et animations
Vue.js permet de gérer des transitions d'éléments lors de l'ajout et de la suppression. Dans cette application, la transition est utilisée pour les éléments de la table (<tr>) lors de l'ajout ou de la suppression d'une facture.

Transition pour l'ajout de factures : Utilisation de la directive transition-group pour appliquer une transition fluide lors de l'entrée des lignes de table.
Transition pour la suppression de factures : Lorsqu'une facture est supprimée, une transition d'opacité est appliquée, créant un effet de disparition en douceur.

6. Styles CSS
Les styles de l'application sont définis dans la section <style scoped>. L'utilisation de scoped garantit que ces styles ne s'appliquent qu'au composant actuel. Voici une description détaillée des styles appliqués.

Style global
 
Propriétés :
•	Fond clair (#f4f7fa).
•	Ombre subtile autour du conteneur principal pour ajouter de la profondeur.
•	Le conteneur est centré et limité à une largeur maximale de 900px.

Formulaire d'ajout de facture
 
Propriétés :
o	Fond blanc pour le formulaire.
o	Ombre légère pour séparer visuellement le formulaire du reste de la page.
o	L'effet scale(1.02) lors du survol pour ajouter un effet interactif.

Tableau des factures
 
Propriétés :
o	Le tableau utilise une largeur de 100% pour s'adapter à son conteneur.
o	Chaque cellule de tableau a un remplissage de 12px pour améliorer la lisibilité.
o	Les lignes du tableau changent de couleur au survol.
 
Effets d'animation
Les transitions sont définies pour les éléments de la table :
 
Propriétés :
o	L'effet de fade-in et fade-out est appliqué lors de l'ajout et de la suppression de lignes du tableau.

7. Améliorations et fonctionnalités futures
Voici quelques idées d'amélioration et de fonctionnalités futures pour l'application :
1.	Validation de formulaire avancée : Ajouter une validation côté client pour garantir que les valeurs du formulaire sont correctement formatées avant de les envoyer.
2.	Stockage persistant : Utiliser localStorage ou une base de données pour stocker les factures de manière persistante entre les sessions.
3.	Ajout de fonctionnalités de recherche et de filtre : Permettre à l'utilisateur de rechercher ou filtrer les factures par nom, date ou montant.
4.	Modification des factures : Ajouter la possibilité de modifier une facture existante.


Remarques
•	Réinitialisation des données : Les données des factures sont stockées uniquement dans la mémoire du navigateur. Si vous rechargez la page, toutes les factures seront perdues. Il est possible d'ajouter des fonctionnalités de stockage persistant (par exemple, localStorage ou une API) pour rendre les factures persistantes.
