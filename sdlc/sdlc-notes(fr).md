# Cycle de Vie du Développement Logiciel (SDLC)

Ce document présente ma compréhension du **Software Development Life Cycle (SDLC)**
à travers un **projet simple basé sur NestJS**, où les pratiques **DevOps sont clairement visibles**.


## Projet Exemple utilisé dans ce SDLC

#### Teacher Availability API (Projet simple DevOps – NestJS)

> Un service backend léger développé avec **NestJS** qui permet :

* d’enregistrer des enseignants
* de définir leurs disponibilités
* de permettre aux parents de consulter les enseignants disponibles
* d’exposer un endpoint de vérification de l’état de l’application

Ce projet est volontairement simple sur le plan fonctionnel, mais solide du point de vue **DevOps**.


### 1. Planification (Planning)

**Objectif :** Définir pourquoi le logiciel est développé et pour qui.

#### Activités clés :

* Identifier l’objectif de l’application
* Définir les utilisateurs cibles (parents et enseignants)
* Définir les attentes en termes de disponibilité et de fiabilité
* Identifier les contraintes techniques

#### Livrables :

* Vision du projet
* Feuille de route globale
* Indicateurs de succès (disponibilité de l’API, temps de réponse)

#### Application au projet :

* L’API doit être hautement disponible
* Le déploiement doit être automatisé
* Le système doit être facilement observable


### 2. Analyse des besoins (Requirement Analysis)

**Objectif :** Définir ce que le système doit faire.

#### Exigences fonctionnelles :

* Créer et lister des enseignants
* Créer et consulter les disponibilités
* Fournir un endpoint `/health`

#### Exigences non fonctionnelles :

* Temps de réponse inférieur à 200 ms
* Application conteneurisée (Docker)
* Configuration par variables d’environnement
* Journalisation (logs) et monitoring activés

#### Livrables :

* Spécification des exigences logicielles (SRS)
* Définition des endpoints API

#### Outils :

* Git pour le contrôle de version
* Suivi des tâches (issues, user stories)


### 3. Conception (Design)

**Objectif :** Définir comment le système va fonctionner.

#### Architecture :

```
Client → API NestJS → Base de données
```

#### Décisions de conception :

* API REST développée avec NestJS
* Architecture modulaire (modules, contrôleurs, services)
* Docker pour la conteneurisation
* Docker Compose pour l’orchestration locale
* Utilisation de variables d’environnement

#### Livrables :

* Diagramme d’architecture
* Dockerfile (NestJS)
* docker-compose.yml


### 4. Implémentation (Développement)

**Objectif :** Construire l’application.

#### Activités clés :

* Développement des modules NestJS
* Création des contrôleurs et services
* Écriture de tests unitaires basiques
* Gestion du code avec Git (branches, commits clairs)

#### Pratiques DevOps :

* Intégration continue (CI)
* Tests automatisés
* Linting et formatage du code


### 5. Pipeline CI/CD

**Objectif :** Automatiser la construction, les tests et le déploiement.

#### Étapes du pipeline :

1. Installation des dépendances
2. Exécution des tests
3. Build de l’application NestJS
4. Construction de l’image Docker
5. Vérification du démarrage du conteneur

#### Outils :

* GitHub Actions
* Docker
* NestJS CLI


### 6. Déploiement

**Objectif :** Livrer l’application de manière fiable.

#### Activités clés :

* Déploiement automatisé via Docker Compose
* Séparation des environnements (dev / prod)
* Gestion de la configuration par variables d’environnement

#### Livrables :

* Conteneurs en fonctionnement
* Images Docker versionnées


### 7. Maintenance et Supervision (Monitoring)

**Objectif :** Assurer la stabilité du système et son amélioration continue.

#### Activités clés :

* Surveillance de l’état de l’application
* Analyse des logs
* Correction des bugs
* Optimisation des performances
* Mises à jour de sécurité

#### Outils :

* Endpoint `/health` avec **NestJS Terminus**
* Prometheus et Grafana (dashboards simples)
* Logs Docker


### Rôle de DevOps dans le SDLC

DevOps est présent à toutes les étapes du cycle de vie :

* **Planification** : anticipation de la fiabilité et de l’automatisation
* **Conception** : architecture orientée conteneurs
* **Développement** : intégration continue et qualité du code
* **Déploiement** : livraison automatisée
* **Maintenance** : monitoring et observabilité
