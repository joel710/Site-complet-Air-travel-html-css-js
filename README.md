# Application de Gestion d'Agence de Voyage

## 1. Vue d'ensemble du Projet

Ce projet vise à développer une application web complète pour la gestion d'une agence de voyage. L'application est conçue pour servir à la fois les clients souhaitant réserver des voyages et le personnel de l'agence (agents, administrateurs) gérant les opérations.

**Note Importante sur le Backend :** L'analyse détaillée et la documentation du backend n'ont pas pu être réalisées car les fichiers sources du backend n'étaient pas disponibles dans le répertoire `Projet back-end/reservation-pro/` au moment de l'analyse. Par conséquent, cette documentation se concentre principalement sur le frontend et les spécifications fonctionnelles générales.

Les fonctionnalités clés envisagées incluent :
*   Gestion des réservations en ligne
*   Gestion des clients
*   Gestion des paiements et facturation
*   Gestion des vols
*   Gestion des agents et des utilisateurs du système
*   Gestion des destinations

## 2. Frontend

### 2.1. Structure et Technologie

Le frontend est actuellement constitué d'un ensemble de pages HTML statiques situées dans le répertoire `frontend/`.

*   **Technologie principale :** HTML
*   **Styling :** [Tailwind CSS](https://tailwindcss.com/) (chargé via CDN). Quelques styles CSS personnalisés mineurs sont présents de manière inline ou dans des balises `<style>` sur certaines pages (ex: `frontend/admin.html`, `frontend/client_dashboard.html`).
*   **Scripting :**
    *   Aucun fichier JavaScript (`.js`) ou TypeScript (`.ts`) personnalisé externe n'a été trouvé dans la structure du projet.
    *   La page `frontend/admin.html` contient du JavaScript embarqué pour :
        *   L'initialisation et l'affichage d'un graphique de revenus à l'aide de [Chart.js](https://www.chartjs.org/) (avec des données statiques).
        *   La gestion de l'affichage/masquage de la barre latérale de navigation en mode mobile.
        *   Un exemple de fonctionnalité de bascule pour un mode sombre (dark mode).
    *   Les autres pages sont principalement statiques, avec une interactivité limitée aux liens de navigation HTML standards.
*   **Architecture :** Application multi-pages (MPA). Il n'y a pas de framework frontend moderne (comme React, Angular, Vue.js) utilisé.
*   **Ressources :** Les images et une vidéo sont stockées dans `frontend/images/`. Les icônes Font Awesome sont utilisées sur la page `admin.html` (chargées via CDN).

### 2.2. Pages Frontend et Fonctionnalités

Le répertoire `frontend/` contient les pages HTML suivantes :

*   `index.html`: Page d'accueil principale présentant l'agence, les destinations populaires, les offres spéciales et les témoignages.
*   `client_dashboard.html`: Tableau de bord pour les clients connectés, affichant (de manière statique) les réservations, l'historique des voyages et des paiements.
*   `admin.html`: Tableau de bord d'administration complet avec des statistiques (statiques), un graphique de revenus, la gestion des réservations récentes et le statut des vols. Utilise Chart.js et du JavaScript personnalisé pour l'interactivité de l'interface utilisateur.
*   `agents.html`: Portail pour les agents, incluant un formulaire de connexion et une maquette de tableau de bord pour la gestion des réservations, clients, paiements, etc.
*   `clients.html`: Interface pour la gestion des clients (liste, recherche, ajout de nouveaux clients - formulaires statiques).
*   `destinations.html`: Interface pour la gestion des destinations de voyage (liste, ajout/modification - formulaires statiques).
*   `flights.html`: Interface pour la gestion des vols (liste, ajout/modification - formulaires statiques).
*   `payments.html`: Interface pour la gestion et la consultation de l'historique des paiements, avec des filtres et des exemples de factures (statiques).
*   `reservations.html`: Interface pour la gestion des réservations (liste, filtres, création de nouvelles réservations - formulaires statiques).

La hiérarchie des fichiers est plate, les pages HTML étant à la racine de `frontend/`. Les "composants" (comme les en-têtes, pieds de page) sont recréés dans chaque fichier plutôt que d'être des modules réutilisables.

### 2.3. Instructions de Configuration et d'Exécution du Frontend

1.  **Aucune étape de build n'est nécessaire** car les pages sont statiques et les dépendances (Tailwind CSS, Chart.js, Font Awesome) sont chargées via CDN.
2.  Pour visualiser le frontend :
    *   Clonez ce dépôt (si ce n'est pas déjà fait).
    *   Ouvrez les fichiers `.html` du répertoire `frontend/` directement dans un navigateur web.
    *   Par exemple, ouvrez `frontend/index.html` pour voir la page d'accueil.

## 3. Backend (Non analysé)

Comme mentionné, le code source du backend (attendu dans `Projet back-end/reservation-pro/`) n'a pas pu être localisé. Une analyse détaillée, la documentation des API, des entités, des processus et la création d'un diagramme de classes pour le backend n'ont donc pas été possibles.

L'application nécessiterait un backend robuste (par exemple, basé sur Spring Boot comme suggéré dans la demande initiale) pour gérer :
*   L'authentification et l'autorisation des utilisateurs (clients, agents).
*   La persistance des données (clients, vols, réservations, paiements, destinations) dans une base de données relationnelle.
*   La logique métier pour toutes les fonctionnalités décrites dans le Cahier des Charges.
*   Les API REST pour la communication avec le frontend.

## 4. Documentation Complémentaire

*   **`Cahier_des_Charges.md`**: Ce fichier (à la racine du projet) contient les spécifications fonctionnelles détaillées, les objectifs, les règles de gestion et les contraintes techniques du projet.
*   **`UseCaseDiagram.md`**: Ce fichier (à la racine du projet) fournit une description textuelle des diagrammes de cas d'utilisation UML, identifiant les acteurs et leurs interactions avec le système.
*   **`Frontend_Analysis.md`**: Ce fichier (à la racine du projet) détaille l'analyse de la structure et des processus du frontend.

## 5. Diagrammes UML

*   **Diagramme de Cas d'Utilisation**: Décrit textuellement dans `UseCaseDiagram.md`.
*   **Diagramme de Classes**: N'a pas pu être créé en raison de l'absence du code source du backend.

## 6. Pistes d'Amélioration Suggérées (basées sur l'analyse actuelle)

*   **Frontend**:
    *   Mettre en place un système de templating (même simple, côté client ou via un générateur de site statique) pour éviter la duplication des en-têtes, pieds de page et barres de navigation.
    *   Relier les formulaires à des appels API backend une fois celui-ci développé.
    *   Si des "scripts TypeScript pour les processus" sont souhaités, il faudrait introduire TypeScript dans le projet frontend, configurer un processus de compilation, et développer ces scripts pour gérer la logique côté client (validation de formulaires plus poussée, interactions dynamiques, appels API, gestion d'état).
*   **Backend**:
    *   Développer le backend en suivant les spécifications du Cahier des Charges, en utilisant par exemple Spring Boot et une base de données relationnelle.
    *   Définir et documenter clairement les API REST pour l'interaction avec le frontend.
