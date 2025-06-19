# Cahier De Charge : Gestion d’une agence de voyage

## I / Objectifs

Développer une application web qui permet de gérer une agence de voyage. Les principaux objectifs sont :

1.  **Gérer les réservations en ligne :** Permettre aux clients de réserver des vols et des séjours, et aux agents de gérer ces réservations.
2.  **Gérer les clients :** Maintenir une base de données des clients, incluant leurs informations personnelles et leur historique de voyage.
3.  **Gérer le paiement :** Faciliter le processus de paiement des réservations et suivre l'historique des transactions.
4.  **Gérer les vols :** Administrer les informations sur les vols disponibles, y compris les horaires, les destinations et les places.
5.  **Gérer les agents :** Permettre la gestion des utilisateurs du système avec différents rôles (ex : administrateur, comptable, agent de réservation).
6.  **Gérer les destinations :** Maintenir une liste des destinations de voyage proposées par l'agence.

## II / Les Règles de gestion

1.  Un client peut faire une ou plusieurs réservations.
2.  Dans un vol il y a un ou plusieurs clients (passagers).
3.  Un vol fait objet d’un ou plusieurs types de billets (ex: classe économique, affaire, première classe - *inférence basée sur la pratique courante, non explicite dans le texte initial*).
4.  Dans une réservation, un client peut réserver une ou plusieurs places.
5.  Un agent peut gérer une ou plusieurs réservations/clients/vols (selon son rôle et ses permissions - *inférence*).
6.  Un vol concerne une et une seule destination (pour un trajet direct donné - *inférence pour clarification*).

## III / Les Fonctionnalités

### Gestion des clients

*   **Enregistrement :** Permettre l'ajout de nouveaux clients avec leurs informations (nom, prénom, coordonnées).
*   **Modification :** Permettre la mise à jour des informations d'un client existant.
*   **Suppression :** Permettre la suppression d'un client (en respectant les contraintes d'intégrité des données, par exemple, un client avec des réservations actives ne devrait pas être supprimable directement - *inférence de bonne pratique*).
*   **Affichage :** Lister tous les clients et afficher les détails d'un client spécifique, y compris son historique de voyage.
*   **Rechercher un client :** Fonctionnalité de recherche pour trouver rapidement un client par nom, prénom ou autres critères pertinents.

### Réservation

*   **Création d’une réservation :** Permettre la création d'une nouvelle réservation en spécifiant le client, la destination (implicitement via le vol), la date (implicitement via le vol), et le nombre de places.
*   **Suivi du statut de réservation :** Gérer et afficher différents statuts pour une réservation (en cours, en attente de paiement, confirmé, annulé).
*   **Historique de réservation :**
    *   Consulter l'historique des réservations pour un client spécifique.
    *   Consulter l'ensemble des réservations pour les administrateurs/agents.

### Gestion des destinations

*   **Ajout :** Permettre l'ajout de nouvelles destinations.
*   **Modification :** Permettre la mise à jour des informations d'une destination existante.
*   **Suppression :** Permettre la suppression d'une destination (avec vérification des dépendances, ex: vols associés - *inférence de bonne pratique*).

### Gestion des paiements

*   **Génération automatique des factures :** Le système doit générer automatiquement une facture après la validation (confirmation) de la réservation.
*   **Historique des paiements :**
    *   Consulter l'historique des paiements par client.
    *   Consulter l'historique général des paiements (pour administrateurs/comptables).
    *   Filtrer l'historique des paiements par agent et par intervalle de temps.

## IV / Contraintes Techniques

1.  **Multiutilisateur :** L'application doit supporter plusieurs utilisateurs simultanément avec des rôles et permissions distincts (clients, agents, administrateurs).
2.  **Accès par Navigateur :** L'application doit être accessible via un navigateur web standard.
3.  **Base de données Relationnelle :** Les données de l'application devront être stockées dans une base de données relationnelle.
4.  **Document technique :** Fournir une documentation technique du système.
5.  **Guide d’utilisateur :** Fournir un guide d'utilisateur pour les différentes catégories d'utilisateurs.
