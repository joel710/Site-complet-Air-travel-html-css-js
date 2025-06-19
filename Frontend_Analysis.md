# Analyse du Frontend

## 1. Structure Générale et Technologies

*   **Type de Projet :** Application web multi-pages (MPA) statique.
*   **Répertoire Principal :** `frontend/`
*   **Technologies Primaires :** HTML5.
*   **Styling :**
    *   [Tailwind CSS](https://tailwindcss.com/) chargé via CDN (`<script src="https://cdn.tailwindcss.com"></script>`). La majorité du style est appliquée via des classes utilitaires directement dans le HTML.
    *   Quelques styles CSS personnalisés additionnels sont présents de manière inline ou dans des balises `<style>` sur certaines pages (ex: `frontend/client_dashboard.html` pour les badges de statut, `frontend/admin.html` pour la sidebar et le conteneur de graphique).
*   **Scripting Client :**
    *   **Absence de fichiers `.js` ou `.ts` externes dédiés :** Aucune trace de fichiers JavaScript ou TypeScript personnalisés séparés n'a été trouvée dans l'arborescence du projet `frontend/`.
    *   **JavaScript Embarqué :** La page `frontend/admin.html` contient du code JavaScript embarqué notable pour :
        *   L'intégration de la librairie [Chart.js](https://www.chartjs.org/) (via CDN) pour l'affichage d'un graphique de revenus (les données du graphique sont statiques dans le script).
        *   La gestion de l'interactivité de l'interface utilisateur, notamment le basculement de la visibilité d'une barre latérale de navigation pour les écrans mobiles.
        *   Un exemple de code pour une fonctionnalité de bascule de mode sombre (dark mode).
    *   Les autres pages HTML ne présentent pas de scripts personnalisés significatifs et reposent sur les fonctionnalités standards du navigateur et de Tailwind CSS.
*   **Framework Frontend :** Aucun framework JavaScript moderne (tel que React, Angular, Vue.js) n'est utilisé.
*   **Structure des Fichiers :**
    *   Les fichiers HTML sont situés directement à la racine du répertoire `frontend/`.
    *   Un sous-répertoire `frontend/images/` contient les ressources graphiques (images JPG, une vidéo MP4).
*   **Icônes :** [Font Awesome](https://fontawesome.com/) est utilisé sur la page `admin.html` (chargé via CDN).

## 2. Organisation des Pages et Composants

*   **Pages :** Chaque fichier `.html` dans `frontend/` représente une page distincte de l'application.
    *   `index.html`: Page d'accueil.
    *   `client_dashboard.html`: Tableau de bord client.
    *   `admin.html`: Tableau de bord administrateur.
    *   `agents.html`: Espace agent (connexion et maquette de tableau de bord).
    *   `clients.html`: Gestion des clients.
    *   `destinations.html`: Gestion des destinations.
    *   `flights.html`: Gestion des vols.
    *   `payments.html`: Gestion des paiements et factures.
    *   `reservations.html`: Gestion des réservations.
*   **Composants :** Le concept de "composants" réutilisables au sens des frameworks modernes n'est pas appliqué. Les sections communes telles que l'en-tête (`<header>`) et le pied de page (`<footer>`) sont dupliquées dans chaque fichier HTML. Les éléments d'interface sont construits avec du HTML standard et des classes Tailwind CSS.

## 3. Processus et Flux Utilisateur (Frontend)

*   **Navigation :** La navigation entre les pages se fait via des liens hypertextes (`<a>`) standards.
*   **Interaction Utilisateur :**
    *   Les formulaires HTML (`<form>`) sont présents sur de nombreuses pages (connexion, ajout/modification de clients, vols, destinations, réservations, filtres). Actuellement, ces formulaires ont leurs attributs `action` définis sur `"#"` et ne soumettent pas de données à un backend ni n'exécutent de logique de traitement côté client avancée.
    *   La page `admin.html` offre une interactivité plus riche grâce à JavaScript pour son graphique et sa barre latérale.
*   **Données Affichées :** Toutes les données présentées dans les listes, tableaux et graphiques sont des données statiques (placeholders) intégrées directement dans le code HTML ou les scripts embarqués. Il n'y a pas d'appel à des API externes pour récupérer des données dynamiques.

## 4. Scripts TypeScript pour les Processus

Conformément à la demande initiale de documenter "les script typescript pour les processuce", l'analyse a révélé **qu'il n'existe pas de fichiers TypeScript (`.ts`) dédiés** dans la structure actuelle du projet frontend. La logique de script existante est en JavaScript et est embarquée dans `admin.html`.

Si des processus métier plus complexes ou une gestion d'état côté client sont requis via TypeScript, cela nécessiterait l'intégration de TypeScript dans le workflow de développement frontend (compilation, etc.) et la création de nouveaux scripts.
