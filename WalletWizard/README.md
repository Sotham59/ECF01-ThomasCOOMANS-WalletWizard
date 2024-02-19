# Wallet-Wizard

Objectifs
Créer une application web simple pour suivre les dépenses personnelles. 

Utiliser Vue.js pour construire l’interface utilisateur réactive.


Maitriser la notion de composants.


Sujet:  

Vous devez développer une application de gestion des dépenses qui permettra aux utilisateurs de :

Ajouter une nouvelle dépense avec une description et un montant.

Afficher l'historique des dépenses enregistrées.

Calculer le total des dépenses.

Afficher les opérations de crédit et de débit indépendemment (argent entrant et sortant). 

Veillez à soigner l'UI/UX de l'application.

## Installation

1. Télécharger le dossier complet.
2. Le mettre dans un dossier de votre choix sur votre ordinateur
3. Ouvrir un terminal du dossier
4. Lancer l'installation avec la commande :
```bash
npm i
```
5. Puis ce déplacer dans le dossier de l'application.
6. Lancer l'application avec la commande:
```bash
npm run dev
```
7. Ouvrir l'application en local avec le lien present dans le terminal.
  

## Fonctionnement de l'application

L'application permet à l'utilisateur de rentrer un montant en crédit ou en debit.

A chaque ajout, une card est créer en dessous en affichant le titre, la description et le montant.

Au dessus de chaque colonne, le cumule des débits ou crédit est affichés.

En haut, le solde du compte est afficher et ce met a jour automatiquement lors de l'ajout ou la suppression d'une card.


## Composition de l'application

Toute l'application à été faite en VueJS.

L'application est composée de plusieurs composants. Un formulaire et un card pour l'operation de debit et idem pour l'opération de crédit.

