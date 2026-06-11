# **Dossier de Conception – StudyFlow AI**

**Version 1.0** | **Date : 10 juin 2026** **Auteur : NovaLab Didier Chardonnet**


# **Table des Matières**


1. **[Analyse du problème utilisateur**](#1-analyse-du-problème-utilisateur)

   - 1.1. [Contexte général](#11-contexte-général)

   - 1.2. [Détail des problématiques](#12-détail-des-problématiques)

   - 1.3. [Synthèse des problématiques](#13-synthèse-des-problématiques)

   - 1.4. [Opportunités pour StudyFlow AI](#14-opportunités-pour-studyflow-ai)

   - 1.5. [Outils actuellement utilisés par les étudiants](#15-outils-actuellement-utilisés-par-les-étudiants)

   - 1.6. [Fonctionnalités clés de StudyFlow AI](#16-fonctionnalités-clés-de-studyflow-ai)

   - 1.7. [Composants techniques](#17-composants-techniques)

   - 1.8. [Intégration de l’IA](#18-intégration-de-lia)

   - 1.9. [Structure et types de données collectées](#19-structure-et-types-de-données-collectées)

2. **[Les profils utilisateurs et leurs besoins**](#2-les-profils-utilisateurs-et-leurs-besoins)

   - 2.1. [Cartographie des utilisateurs](#21-cartographie-des-utilisateurs)

   - 2.2. [Persona primaire détaillé : Lucas Moreau](#22-persona-primaire-détaillé-lucas-moreau)

   - 2.3. [Personas secondaires](#23-personas-secondaires)

     - 2.3.1. [Marie Dupont](#231-marie-dupont)

     - 2.3.2. [Antoine Lefèvre](#232-antoine-lefèvre)

     - 2.3.3. [Jean-Luc Bernard](#233-jean-luc-bernard)

   - 2.4. [Besoins consolidés](#24-besoins-consolidés)

   - 2.5. [Hypothèses à valider](#25-hypothèses-à-valider)

   - 2.6. [Scénarios concrets d’usage](#26-scénarios-concrets-dusage)

3. **[Liste des fonctionnalités du produit**](#3-liste-des-fonctionnalités-du-produit)

   - 3.1. [Fonctionnalités Core (MVP V1)](#31-fonctionnalités-core-mvp-v1)

   - 3.2. [Fonctionnalités Importantes (Améliorations significatives)](#32-fonctionnalités-importantes-améliorations-significatives)

   - 3.3. [Fonctionnalités Nice-to-Have (Valeur future)](#33-fonctionnalités-nice-to-have-valeur-future)

   - 3.4. [Priorisation et Backlog](#34-priorisation-et-backlog)

   - 3.5. [Analyse de complexité](#35-analyse-de-complexité)

4. **[Architecture de l’application et parcours utilisateurs**](#4-architecture-de-lapplication-et-parcours-utilisateurs)

   - 4.1. [Introduction](#41-introduction)

   - 4.2. [Sitemap (Structure des pages)](#42-sitemap-structure-des-pages)

     - 4.2.1. [Pages publiques (avant connexion)](#421-pages-publiques-avant-connexion)

     - 4.2.2. [Espace connecté (après connexion)](#422-espace-connecté-après-connexion)

     - 4.2.3. [Paramètres](#423-paramètres)

     - 4.2.4. [Administration](#424-administration)

   - 4.3. [Parcours utilisateurs (User Flows)](#43-parcours-utilisateurs-user-flows)

     - 4.3.1. [Flow 1 : Connexion / Identification de l’utilisateur](#431-flow-1-connexion--identification-de-lutilisateur)

     - 4.3.2. [Flow 2 : Nouvelle tâche et planification](#432-flow-2-nouvelle-tâche-et-planification)

     - 4.3.3. [Flow 3 : Gestion des ressources](#433-flow-3-gestion-des-ressources)

   - 4.4. [Structure de navigation](#44-structure-de-navigation)

     - 4.4.1. [Menu principal (Sidebar)](#441-menu-principal-sidebar)

     - 4.4.2. [Éléments toujours visibles vs contextuels](#442-éléments-toujours-visibles-vs-contextuels)

     - 4.4.3. [Patterns de navigation](#443-patterns-de-navigation)

   - 4.5. [Justification des choix pour le persona primaire](#45-justification-des-choix-pour-le-persona-primaire)

   - 4.6. [Audit de l’architecture](#46-audit-de-larchitecture)

     - 4.6.1. [Points forts](#461-points-forts)

     - 4.6.2. [Axes d’amélioration](#462-axes-damélioration)

   - 4.7. [Synthèse et prochaines étapes](#47-synthèse-et-prochaines-étapes)

5. **[Modèle conceptuel de données**](#5-modèle-conceptuel-de-données)

   - 5.1. [Introduction](#51-introduction)

   - 5.2. [Entités principales et relations](#52-entités-principales-et-relations)

   - 5.3. [Vérification de cohérence du modèle](#53-vérification-de-cohérence-du-modèle)

   - 5.4. [Croisement de cohérence et corrections](#54-croisement-de-cohérence-et-corrections)

   - 5.5. [Script SQL de création de la base de données](#55-script-sql-de-création-de-la-base-de-données)

   - 5.6. [Schéma visuel du modèle conceptuel](#56-schéma-visuel-du-modèle-conceptuel)

   - 5.7. [Conventions et bonnes pratiques](#57-conventions-et-bonnes-pratiques)

6. **[Description des fonctionnalités intégrant l’intelligence artificielle**](#6-description-des-fonctionnalités-intégrant-lintelligence-artificielle) *(Chapitre actuel)*

   - 6.1. [Introduction](#61-introduction)

   - 6.2. [Opportunités clés pour l’IA dans StudyFlow AI](#62-opportunités-clés-pour-lia-dans-studyflow-ai)

   - 6.3. [Comparaison des approches pour l’intégration de l’IA](#63-comparaison-des-approches-pour-lintégration-de-lia)

   - 6.4. [Approche hybride recommandée pour le MVP](#64-approche-hybride-recommandée-pour-le-mvp)

   - 6.5. [Challenge des pertinences et limites de l’IA](#65-challenge-des-pertinences-et-limites-de-lia)

   - 6.6. [Note de conception IA : Intégration technique](#66-note-de-conception-ia-intégration-technique)

   - 6.7. [Cas d’usage concrets avec l’IA](#67-cas-dusage-concrets-avec-lia)

   - 6.8. [Risques et solutions associés](#68-risques-et-solutions-associés)

   - 6.9. [KPIs et métriques de succès](#69-kpis-et-métriques-de-succès)


# 1. Analyse du problème utilisateur


## 1.1. Contexte général

StudyFlow AI est une application conçue pour répondre aux **défis majeurs** rencontrés par les étudiants dans leur organisation, leur apprentissage et leur gestion du temps. Les problématiques identifiées sont classées en **4 catégories principales** :

| **Catégorie** | **Problématiques clés** | **Impact sur l’étudiant** |
| :-: | :-: | :-: |
| **Organisation** | Manque de structuration globale, difficulté à prioriser les tâches, surcharge cognitive. | Stress, oublis, résultats sous-optimaux. |
| **Motivation et régularité** | Manque de motivation, procrastination, difficulté à évaluer ses progrès. | Abandon des révisions, stress de dernière minute. |
| **Outils existants** | Outils non intégrés, manque de personnalisation, interfaces complexes, manque de collaboration. | Perte de temps, inefficacité, frustration. |
| **Apprentissage** | Difficulté à comprendre les concepts complexes, manque de ressources adaptées, difficulté à rester concentré, manque de méthodologie. | Apprentissage superficiel, baisse de productivité. |


## 1.2. Détail des problématiques

### 1.2.1. Problématiques liées à l’organisation

- **Manque de structuration globale** : Les étudiants peinent à avoir une **vue d’ensemble** de leurs cours, tâches et échéances. Ils utilisent souvent des outils séparés (Google Calendar, OneNote, etc.) qui ne communiquent pas entre eux.

- **Exemple** : Un étudiant doit gérer 5 matières pour un examen dans 2 semaines, mais ne sait pas comment répartir son temps.

- **Impact** : Surcharge cognitive, oublis fréquents.

- **Difficulté à prioriser les tâches** : Absence de critères clairs (urgence, importance, difficulté) et manque de visibilité sur les dépendances entre les tâches.

- **Exemple** : Une tâche urgente (devoir à rendre demain) peut être oubliée au profit d’une tâche moins importante mais plus simple.

- **Impact** : Stress accru, résultats sous-optimaux.

- **Surcharge cognitive** : Multiplicité des supports (PDF, vidéos, notes manuscrites) et manque de synthèse.

- **Exemple** : Un étudiant en médecine doit mémoriser des centaines de pages sans outil pour identifier les concepts clés.

- **Impact** : Perte de motivation, baisse d’efficacité.

### 1.2.2. Problématiques liées à la motivation et à la régularité

- **Manque de motivation** : Absence de feedback immédiat ou de récompenses pour les efforts fournis.

- **Impact** : Abandon des révisions.

- **Procrastination** : Les tâches difficiles ou peu motivantes sont repoussées.

- **Impact** : Stress de dernière minute.

- **Difficulté à évaluer ses progrès** : Les étudiants ne savent pas mesurer leur avancée ou identifier leurs lacunes.

- **Impact** : Fausse confiance ou doute permanent.

### 1.2.3. Problématiques liées aux outils existants

- **Outils non intégrés** : Les étudiants doivent basculer entre plusieurs applications (Google Calendar, Notion, Anki, etc.).

- **Impact** : Perte de temps, double saisie.

- **Manque de personnalisation** : Les outils génériques ne s’adaptent pas aux besoins spécifiques des étudiants.

- **Impact** : Efficacité réduite.

- **Interfaces complexes** : Les fonctionnalités avancées sont souvent difficiles à maîtriser.

- **Impact** : Abandon de l’outil.

- **Manque de collaboration** : Peu de fonctionnalités pour partager des ressources ou travailler en groupe.

- **Impact** : Apprentissage moins efficace.

### 1.2.4. Problématiques liées à l’apprentissage

- **Difficulté à comprendre les concepts complexes** : Besoin de reformulations ou d’exemples concrets.

- **Impact** : Blocages dans l’apprentissage.

- **Manque de ressources adaptées** : Les ressources disponibles (vidéos, exercices) ne correspondent pas toujours au niveau ou aux besoins de l’étudiant.

- **Impact** : Perte de temps.

- **Difficulté à rester concentré** : Distractions numériques (réseaux sociaux, notifications) et manque de structure.

- **Impact** : Baisse de productivité.

- **Manque de méthodologie** : Absence de techniques de travail (Pomodoro, répétition espacée, etc.).

- **Impact** : Apprentissage inefficace.

## 1.3. Synthèse des problématiques

Pour résumer, les étudiants rencontrent des **obstacles majeurs** dans 4 domaines :

1. **Organisation** : Manque de centralisation et de priorisation.

2. **Motivation** : Absence de feedback et de récompenses.

3. **Outils** : Fragmentation, manque de personnalisation et de collaboration.

4. **Apprentissage** : Ressources inadaptées, manque de méthodologie.

**Solution proposée par StudyFlow AI** : Une **plateforme unifiée**, **personnalisée** et **collaborative**, intégrant l’IA pour centraliser les outils, automatiser la planification, motiver via des feedbacks, et collaborer via des groupes.

## 1.4. Opportunités pour StudyFlow AI

À partir de cette analyse, StudyFlow AI peut répondre aux besoins suivants :

| **Opportunité** | **Description** | **Bénéfice pour l’étudiant** |
| :-: | :-: | :-: |
| **Centralisation** | Une seule plateforme pour gérer notes, tâches, calendrier et ressources. | Gain de temps, réduction du stress. |
| **Personnalisation** | Planning intelligent, ressources adaptées, feedback personnalisé. | Efficacité accrue, apprentissage ciblé. |
| **Motivation** | Système de récompenses, suivi des progrès, rappels intelligents. | Régularité, confiance en soi. |
| **Collaboration** | Partage de ressources, groupes d’entraide, travail en équipe. | Apprentissage collaboratif, entraide. |
| **Apprentissage efficace** | Méthodologies intégrées (Pomodoro, répétition espacée), explications adaptées. | Meilleure assimilation, résultats améliorés. |


## 1.5. Outils actuellement utilisés par les étudiants

Les étudiants utilisent actuellement une **multiplicité d’outils non intégrés**, chacun répondant à un besoin spécifique mais créant des **frictions** (double saisie, manque de synchronisation, interfaces complexes).

| **Outil** | **Type** | **Fonctionnalité principale** | **Limites identifiées** | **Impact** |
| :-: | :-: | :-: | :-: | :-: |
| Google Calendar | Calendrier | Gestion des échéances (cours, examens). | Pas de prise en compte contextuelle des besoins étudiants. | Perte de temps, oublis. |
| OneNote | Notes | Organisation des cours et fiches. | Structure dépendante de l’étudiant : sans rigueur, les notes deviennent chaotiques. | Difficulté à retrouver l’information. |
| Google Mail | Messagerie | Réception des annonces et devoirs. | Boîtes mail mal organisées, absence de purge ou de filtrage intelligent. | Surcharge cognitive. |
| Anki | Révisions (flashcards) | Mémorisation par répétition espacée. | Nécessite une saisie manuelle des cartes, pas d’intégration avec les autres outils. | Travail répétitif. |
| Discord | Collaboration | Communication et partage de ressources. | Pas de structuration des ressources partagées. | Manque d’efficacité collaborative. |
| Notion | Organisation globale | Centralisation des notes et tâches. | Courbe d’apprentissage abrupte, personnalisation complexe. | Abandon par certains utilisateurs. |
| Aucun | Révisions structurées | - | Pas d’outil dédié pour les révisions. | Apprentissage moins efficace. |


**Synthèse** :

- **Fragmentation** : Les étudiants basculent en moyenne entre **4 à 6 outils** différents.

- **Manque d’intégration** : Aucune synchronisation automatique entre ces outils.

- **Personnalisation limitée** : Les outils génériques ne s’adaptent pas aux besoins spécifiques.

- **Collaboration inefficace** : Peu de fonctionnalités pour le travail en groupe.

## 1.6. Fonctionnalités clés de StudyFlow AI

Pour répondre aux problématiques identifiées, StudyFlow AI propose un **ensemble de fonctionnalités** classées par priorité pour le **MVP (V1)** et les versions ultérieures.

| **Fonctionnalité** | **Description** | **Priorité (V1)** | **Complexité** | **Bénéfice utilisateur** |
| :-: | :-: | :-: | :-: | :-: |
| Analyse des objectifs | Analyser les objectifs d’apprentissage de l’étudiant. | ⭐⭐⭐⭐⭐ (1) | ⭐⭐⭐⭐ (4) | Plan de travail personnalisé. |
| Plan de travail personnalisé | Générer un planning adapté aux objectifs, échéances et lacunes. | ⭐⭐⭐⭐⭐ (1) | ⭐⭐⭐ (3) | Optimisation du temps, réduction du stress. |
| Structuration des révisions | Organiser les révisions par matière/thème, avec des rappels intelligents. | ⭐⭐⭐⭐ (2) | ⭐ (1) | Meilleure couverture des sujets. |
| Génération de quiz/exercices | Créer des exercices adaptés au niveau et aux lacunes. | ⭐⭐⭐ (2) | ⭐⭐ (2) | Apprentissage actif et ciblé. |
| Suivi des progrès | Tableau de bord pour visualiser les avancées, les lacunes et les performances. | ⭐⭐⭐⭐ (4) | ⭐⭐ (2) | Motivation, auto-évaluation. |
| Rappels intelligents | Notifications pour les tâches/révisions, basées sur les progrès. | ⭐⭐⭐ (3) | ⭐ (1) | Régularité, réduction de la procrastination. |
| Intégration des outils existants | Synchronisation avec Google Calendar, Notion, etc. | ⭐⭐ (5) | ⭐⭐⭐ (3) | Gain de temps, évite la double saisie. |
| Chatbot IA | Assistant pour poser des questions, obtenir des explications. | ⭐⭐⭐ (2) | ⭐⭐⭐⭐⭐ (5) | Accès immédiat à de l’aide. |
| Collaboration entre étudiants | Partage de fiches, quiz, ressources et organisation de sessions. | ⭐⭐ (5) | ⭐⭐⭐⭐⭐ (5) | Apprentissage collaboratif, entraide. |
| Gestion de documents | Intégrer des documents (PDF, liens web), gérer des fiches. | ⭐⭐⭐ (3) | ⭐⭐ (2) | Centralisation des ressources. |
| Prompts mémorisés | Prompts prédéfinis pour interagir rapidement avec le chatbot. | ⭐ (5) | ⭐⭐⭐ (3) | Gain de temps, interactions fluides. |


**Légende** :

- **Priorité** : ⭐⭐⭐⭐⭐ = Indispensable pour le MVP (V1), ⭐ = Secondaire (V2+).

- **Complexité** : ⭐ = Simple, ⭐⭐⭐⭐⭐ = Complexe.

## 1.7. Composants techniques

L’architecture de StudyFlow AI repose sur une **stack technique moderne**, open source et scalable.

| **Composant** | **Description** | **Technologie suggérée** | **Justification** |
| :-: | :-: | :-: | :-: |
| Frontend | Interface utilisateur (mobile et web) réactive et intuitive. | **Ionic + React** | Compatible multiplateforme (iOS, Android, Web), communauté active. |
| Backend | Logique métier, API REST/GraphQL pour les requêtes. | **Node.js (Express/NestJS)** | Performant, scalable, et compatible avec Supabase. |
| Base de données | Stockage des données utilisateurs, des ressources et des interactions. | **Supabase (PostgreSQL)** | Open source, intégration native avec l’authentification, RLS. |
| Moteur IA | Analyse des données, génération de recommandations, chatbot. | **Mistral AI, Vibe Coding** | Modèles open source, compatibles avec les besoins en français. |
| Authentification | Gestion des comptes utilisateurs. | **Supabase Auth** | Sécurisé, simple à intégrer, compatible avec OAuth. |
| Stockage des fichiers | Stockage des notes, fiches de révision, et ressources partagées. | **Supabase Storage** | Intégré à Supabase, scalable, et sécurisé. |
| Synchronisation | Synchronisation des données avec les outils externes. | **API Google Calendar, Webhooks** | Permet une intégration fluide avec les outils existants. |
| Notifications | Envoi de rappels et alertes (emails, push notifications). | **Firebase Cloud Messaging (FCM)** | Solution open source pour les notifications push. |
| Analyse des données | Suivi des progrès, génération de statistiques. | **Python (Pandas, NumPy)** | Pour les analyses avancées. |


**Schéma d’architecture proposée** :

```
Frontend (Ionic/React) → Backend (Node.js) → Base de données (Supabase)    
                                      ↓    
                              Moteur IA (Mistral AI)    
                                      ↓    
                          Stockage (Supabase Storage)    
                                      ↓    
               Synchronisation (API Google Calendar, Notion)
```

## 1.8. Intégration de l’IA dans StudyFlow AI

L’IA est au cœur de StudyFlow AI pour **automatiser**, **personnaliser** et **optimiser** l’expérience utilisateur.

| **Fonctionnalité** | **Description** | **Modèle/Outils IA** | **Cas d’usage concret** |
| :-: | :-: | :-: | :-: |
| Analyse des objectifs | Comprendre les besoins et objectifs de l’étudiant. | **Mistral AI** | L’étudiant saisit : *"Je veux maîtriser l’algèbre d’ici 2 mois"* → L’IA propose un planning. |
| Génération de quiz | Créer des quiz/exercices personnalisés. | **Mistral AI, GPT** | L’IA génère un quiz sur les dérivées si l’étudiant a des lacunes. |
| Planification intelligente | Optimiser le planning en fonction des échéances et habitudes. | **Agents autonomes (LangChain)** | L’IA détecte que l’étudiant travaille mieux le matin et ajuste les créneaux. |
| Chatbot | Répondre aux questions des étudiants. | **Mistral AI, Vibe Coding** | L’étudiant demande : *"Explique-moi la photosynthèse"* → Le chatbot répond. |
| Détection des schémas | Identifier les habitudes de travail. | **Python (Pandas, Scikit-learn)** | L’IA suggère des pauses si l’étudiant travaille depuis 2h sans interruption. |
| Recommandations de ressources | Proposer des vidéos, fiches ou exercices adaptés. | **Mistral AI** | L’IA recommande une vidéo sur les bases de données si l’étudiant a échoué un quiz. |
| Correction automatique | Corriger les quiz/exercices et fournir des feedbacks. | **Mistral AI** | L’étudiant soumet un exercice → L’IA corrige et explique les erreurs. |


**Flux type avec l’IA** :

1. **Étape 1** : L’étudiant saisit un objectif (ex : *"Réussir mon examen de physique"*).

2. **Étape 2** : L’IA analyse l’objectif et propose un **plan de travail** (ex : *"3 séances de 45 min/semaine"*).

3. **Étape 3** : L’étudiant valide le plan → L’IA génère des **quiz/exercices adaptés**.

4. **Étape 4** : L’IA suit les progrès et **ajuste les recommandations** (ex : *"Tu as des lacunes en mécanique, voici des ressources"*).

## 1.9. Structure et types de données collectées

Pour fonctionner, StudyFlow AI doit collecter et structurer des **données utilisateurs** de manière **sécurisée** (RGPD) et **efficace**.

| **Type de donnée** | **Description** | **Exemple** | **Utilisation** |
| :-: | :-: | :-: | :-: |
| Profil utilisateur | Informations de base pour personnaliser l’expérience. | Nom, âge, niveau d’études. | Adaptation des recommandations. |
| Objectifs d’apprentissage | Cibles à atteindre. | *"Réussir l’examen de physique"* | Génération du plan de travail et des quiz. |
| Calendrier | Dates des cours, examens, révisions et tâches. | *"Examen le 15/06"* | Synchronisation avec les outils externes, rappels intelligents. |
| Notes et ressources | Contenu des cours, fiches de révision, liens. | *"Fiche sur les dérivées"* | Génération de quiz, recommandations de ressources. |
| Résultats de quiz | Scores, temps passé, et performances par matière. | *"85% en quiz d’algèbre"* | Identification des lacunes, ajustement des recommandations. |
| Temps passé | Durée des sessions de travail. | *"2h sur les intégrales"* | Détection des schémas de travail, suggestions d’optimisation. |
| Préférences | Méthodes de travail préférées. | *"Préfère les vidéos aux textes"* | Personnalisation des ressources et du planning. |
| Interactions avec l’IA | Historique des questions posées au chatbot. | *"Explique-moi la photosynthèse"* | Amélioration des réponses du chatbot. |
| Données collaboratives | Ressources partagées, contributions aux groupes. | *"Fiche partagée sur les bases de données"* | Enrichissement des ressources disponibles. |


**Schéma des relations entre les données** :

![Relations entre les données](Graph-Relations.png)

**Sécurité et conformité** :

- **RGPD** : Les données sont **anonymisées** et stockées dans l’UE (via Supabase).

- **Chiffrement** : Toutes les données sensibles (ex : emails) sont chiffrées.

- **Accès contrôlé** : Utilisation de **RLS (Row-Level Security)** dans Supabase pour limiter l’accès aux données.


# 2. Les profils utilisateurs et leurs besoins


## 2.1. Cartographie des utilisateurs

Cette section liste tous les **profils identifiés** pour StudyFlow AI, avec leur type, leur rôle dans le produit et leur statut de priorité pour la **V1**.

\<mui:table-metadata title="Cartographie des utilisateurs" /\>

| **Nom** | **Type** | **Rôle dans le produit** | **Priorité V1** |
| :-: | :-: | :-: | :-: |
| Lucas Moreau | Primaire | Étudiant en formation initiale, utilise toutes les fonctionnalités (organisation, révisions, collaboration). | Inclus |
| Marie Dupont | Primaire | Étudiant en formation continue, besoin de flexibilité et de ressources adaptées. | Inclus |
| Antoine Lefèvre | Primaire | Étudiant en alternance, coordination école/entreprise et suivi des compétences. | Inclus |
| Jean-Luc Bernard | Primaire | Professeur, création de cours, évaluation, suivi des progrès. | Inclus |
| Sophie Lambert | Secondaire | Administrateur d’établissement, gestion des utilisateurs et des cursus. | V2 |
| Claire Moreau | Secondaire | Responsable des stages, organisation des partenariats avec les entreprises. | V2 |



## 2.2. Persona primaire détaillé : Lucas Moreau

### **Profil rapide**

- **Nom** : Lucas Moreau

- **Âge** : 20 ans

- **Formation** : Licence 2 en Informatique à l’Université Paris-Saclay

- **Situation** : Étudiant en formation initiale, vit en colocation, emploi étudiant (10h/semaine)

### **Objectifs principaux**

- Réussir ses examens sans stresser en dernière minute (objectif : moyenne générale \> 14/20).

- Comprendre en profondeur les concepts clés (ex : algorithmes, bases de données).

- Gagner du temps en organisant mieux ses révisions et ses projets (objectif : -50% de temps d’organisation).

- Collaborer efficacement avec ses camarades pour les projets et les révisions.

- Trouver un stage en développement web pour l’été 2027.

### **Frustrations clés**

- **Manque de temps** : Difficulté à concilier cours, révisions, emploi étudiant et vie sociale.

- **Désorganisation** : Oublie souvent ses échéances ou perd ses notes.

- **Surcharge cognitive** : Trop de matières à réviser en parallèle.

- **Manque de ressources adaptées** : Les cours en ligne sont souvent trop théoriques.

- **Difficulté à rester motivé** : Perte de motivation après 2-3 heures de révision.

- **Outils non connectés** : Doit basculer entre Google Calendar, OneNote, Discord et Anki.

### **Comportement numérique**

- Utilisation intensive des outils gratuits (Discord, Anki, GitHub).

- Adoption rapide des nouvelles technologies si elles sont intuitives.

- Préfère les interfaces visuelles (schémas, mind maps).

- Utilise son smartphone pour les rappels et les discussions rapides.

- Partage des ressources via Discord ou WhatsApp.

### **Citation représentative**

> *« J’ai l’impression de passer plus de temps à organiser mes révisions qu’à réviser. Si je pouvais tout centraliser dans un seul outil, avec des rappels intelligents et des ressources adaptées à mon niveau, ce serait parfait. »*

### **Critères de succès**

- Réduction du temps passé à organiser ses révisions (objectif : -50%).

- Amélioration des notes aux examens (objectif : +1 point de moyenne).

- Augmentation de la régularité dans les révisions (objectif : 3 séances/semaine).

- Meilleure collaboration avec ses camarades (objectif : 1 projet groupe réussi/semestre).

- Trouver un stage en développement web (objectif : 1 stage d’ici juin 2027).


## 2.3. Personas secondaires


### 2.3.1. Marie Dupont

#### **Profil rapide**

- **Nom** : Marie Dupont

- **Âge** : 35 ans

- **Formation** : Formation continue en Marketing Digital (en ligne)

- **Situation** : En reconversion professionnelle, mère de 2 enfants, travaille à temps partiel.

#### **Objectifs principaux**

- Obtenir sa certification en marketing digital.

- Trouver un emploi à temps plein d’ici 1 an.

- Réduire de 30% le temps passé à organiser ses études.

#### **Frustrations clés**

- Manque de flexibilité dans les outils existants (ex : impossibilité de planifier des séances courtes).

- Difficulté à trouver des ressources adaptées à son niveau (débutante en marketing digital).

- Manque de temps pour les révisions en raison de ses obligations familiales.

#### **Interaction avec StudyFlow AI**

- Utilise le **planning flexible** pour organiser des séances de 30-45 min.

- Préfère les **ressources courtes** (vidéos, fiches résumées).

- Rejoint des **groupes d’entraide** pour échanger avec d’autres adultes.

- Utilise le **chatbot IA** pour des questions rapides.

#### **Critères de succès**

- Réussir sa certification.

- Trouver un emploi à temps plein d’ici 1 an.

- Réduire de 30% le temps passé à organiser ses études.


### 2.3.2. Antoine Lefèvre

#### **Profil rapide**

- **Nom** : Antoine Lefèvre

- **Âge** : 22 ans

- **Formation** : Alternance en Développement Web à l’École 42

- **Entreprise** : TechSolutions (SSII)

#### **Objectifs principaux**

- Réussir sa formation en alternance.

- Devenir développeur full-stack et décrocher un CDI.

- Appliquer les connaissances théoriques en entreprise.

#### **Frustrations clés**

- Surcharge de travail entre école et entreprise.

- Manque de temps pour les révisions théoriques.

- Difficulté à faire le lien entre théorie et pratique.

#### **Interaction avec StudyFlow AI**

- Utilise le **calendrier partagé** pour synchroniser école et entreprise.

- Suit ses **compétences acquises** en entreprise.

- Rejoint un **groupe d’alternants** pour échanger des conseils.

- Intègre StudyFlow AI avec **Slack et GitHub**.

#### **Critères de succès**

- Obtenir son diplôme en alternance.

- Décrocher un CDI en tant que développeur full-stack.


### 2.3.3. Jean-Luc Bernard

#### **Profil rapide**

- **Nom** : Jean-Luc Bernard

- **Âge** : 45 ans

- **Rôle** : Professeur de Mathématiques et Informatique

- **Établissement** : Université Paris-Saclay

#### **Objectifs principaux**

- Améliorer la réussite de ses étudiants.

- Automatiser les tâches administratives (corrections, suivi des progrès).

- Faciliter la collaboration entre étudiants.

#### **Frustrations clés**

- Temps passé à corriger les copies manuellement.

- Difficulté à suivre les progrès individuels de chaque étudiant.

- Manque d’outils pour personnaliser les supports pédagogiques.

#### **Interaction avec StudyFlow AI**

- Utilise le **tableau de bord des progrès** pour identifier les lacunes des étudiants.

- Crée des **supports pédagogiques** via l’éditeur de cours.

- Automatise les **corrections de quiz** grâce à l’IA.

- Intègre StudyFlow AI avec **Moodle** (plateforme de cours en ligne).

#### **Critères de succès**

- Réduire de 50% le temps passé à corriger les copies.

- Améliorer la moyenne des notes de ses étudiants.

- Augmenter le taux de réussite aux examens.


## 2.4. Besoins consolidés

Voici une **synthèse des besoins** identifiés pour chaque persona, classés par priorité :

| **Besoins** | **Persona** | **Besoins réels** | **Priorité** |
| :-: | :-: | :-: | :-: |
| Centralisation des outils | Lucas | Éviter de basculer entre plusieurs outils. | Haute |
| Calendrier intégré | Lucas, Antoine | Visualiser ses échéances et organiser ses révisions. | Haute |
| Planification intelligente | Lucas, Marie | Générer un plan de révision personnalisé. | Haute |
| Ressources personnalisées | Lucas, Marie | Accéder à des quiz, fiches et vidéos adaptés. | Haute |
| Groupes collaboratifs | Lucas, Antoine | Partager des ressources et organiser des sessions. | Haute |
| Chatbot IA | Lucas, Marie | Obtenir des explications rapides et personnalisées. | Haute |
| Suivi des progrès | Lucas, Antoine, Jean-Luc | Visualiser ses avancées et identifier ses lacunes. | Haute |
| Synchronisation école/entreprise | Antoine | Éviter les conflits entre les calendriers. | Haute |
| Planning flexible | Marie | Organiser des séances d’étude courtes et adaptables. | Moyenne |
| Ressources courtes | Marie | Accéder à des vidéos et fiches résumées (5-10 min). | Moyenne |
| Groupes d’entraide | Marie | Échanger avec d’autres adultes en reconversion. | Moyenne |
| Automatisation des corrections | Jean-Luc | Réduire le temps passé à corriger les copies. | Haute |
| Tableau de bord des progrès | Jean-Luc | Identifier les lacunes des étudiants. | Haute |
| Éditeur de cours | Jean-Luc | Créer des supports pédagogiques. | Moyenne |
| Intégration avec Slack/GitHub | Antoine | Connecter StudyFlow AI à ses outils professionnels. | Moyenne |
| Notifications motivantes | Marie | Recevoir des rappels et encouragements. | Basse |
| Évaluation par les pairs | Lucas, Antoine | Noter les contributions des membres du groupe. | Basse |



## 2.5. Hypothèses à valider

Pour affiner la conception de StudyFlow AI, voici les **hypothèses clés** à valider auprès des utilisateurs :

| **Hypothèse** | **Méthode de validation** | **Persona concerné** |
| :-: | :-: | :-: |
| Les étudiants sont prêts à adopter une nouvelle plateforme si elle centralise tous leurs outils. | Enquête auprès de 50 étudiants (questionnaire en ligne). | Lucas, Marie, Antoine |
| Les étudiants en formation continue préfèrent des séances de révision courtes (30-45 min). | Tests utilisateurs avec des prototypes de planning flexible. | Marie |
| Les professeurs sont prêts à utiliser un outil d’automatisation des corrections. | Entretiens avec 10 professeurs. | Jean-Luc |
| Les étudiants en alternance ont besoin d’un calendrier partagé entre école et entreprise. | Analyse des retours des alternants (focus group). | Antoine |
| Le chatbot IA est perçu comme utile pour obtenir des explications rapides. | Tests utilisateurs avec un prototype de chatbot. | Lucas, Marie |
| Les groupes collaboratifs augmentent la motivation et la réussite des étudiants. | Étude comparative (groupe avec vs sans collaboration). | Lucas, Antoine |



## 2.6. Scénarios concrets d’usage

### **Scénario 1 : Organisation des révisions pour un examen (Lucas)**

**Contexte** : Lucas a un examen de bases de données dans 3 semaines.

**Étapes** :

1. Lucas utilise le **calendrier intégré** de StudyFlow AI pour bloquer des créneaux de révision.

2. L’IA analyse ses objectifs et propose un **plan de travail personnalisé** (3 séances de 2h/semaine).

3. Lucas valide le plan et l’ajoute à son calendrier.

4. Il crée un **groupe de révisions** et invite 4 camarades.

5. Le groupe partage des **fiches** et organise des sessions via le calendrier partagé.

6. Pendant une session, ils utilisent le **tableau blanc collaboratif** pour résoudre des exercices.

7. Lucas passe un **quiz généré par l’IA** pour évaluer ses connaissances.

8. L’IA identifie ses lacunes et recommande des **ressources supplémentaires**.

**Résultat** : Lucas se sent plus confiant et gagne du temps grâce à la collaboration.


### **Scénario 2 : Collaboration sur un projet de développement (Lucas et son équipe)**

**Contexte** : Lucas et son équipe doivent développer une application web.

**Étapes** :

1. Lucas crée un **groupe de projet** et invite ses 3 camarades.

2. Le groupe utilise le **tableau de bord collaboratif** pour répartir les tâches.

3. Ils partagent des **ressources** (liens GitHub, documents) dans l’espace collaboratif.

4. Ils organisent une **session de travail en ligne** via l’outil intégré de visioconférence.

5. Le professeur rejoint le groupe en tant qu’**observateur** et commente les livrables.

**Résultat** : Le projet est finalisé à temps et bien noté.


### **Scénario 3 : Suivi des progrès par un professeur (Jean-Luc)**

**Contexte** : Jean-Luc veut suivre les progrès de ses étudiants en mathématiques.

**Étapes** :

1. Jean-Luc accède au **tableau de bord des progrès** pour visualiser les performances de chaque étudiant.

2. Il identifie les **lacunes** (ex : 60% des étudiants ont des difficultés avec les intégrales).

3. Il génère un **quiz ciblé** sur les intégrales via StudyFlow AI.

4. Les étudiants passent le quiz, et l’IA **corrige automatiquement** les copies.

5. Jean-Luc reçoit un **rapport détaillé** avec les erreurs fréquentes et les progrès.

**Résultat** : Jean-Luc peut adapter ses cours pour répondre aux besoins spécifiques de ses étudiants.


### **Scénario 4 : Planification flexible pour une mère active (Marie)**

**Contexte** : Marie doit réviser pour sa certification en marketing digital, mais elle a peu de temps.

**Étapes** :

1. Marie utilise le **planning flexible** pour bloquer des séances de 30-45 min dans son emploi du temps chargé.

2. L’IA propose des **ressources courtes** (vidéos de 10 min, fiches résumées) adaptées à son niveau.

3. Marie rejoint un **groupe d’entraide** pour échanger avec d’autres adultes en reconversion.

4. Elle utilise le **chatbot IA** pour obtenir des explications rapides sur des concepts complexes.

5. Elle reçoit des **notifications motivantes** pour rester régulière dans ses révisions.

**Résultat** : Marie réussit à concilier ses obligations familiales et ses révisions, et obtient sa certification.


# 3. Liste des fonctionnalités du produit


## 3.1. Fonctionnalités Core (MVP V1)

Les fonctionnalités **Core** sont **indispensables** pour le **MVP (V1)**. Elles répondent aux besoins fondamentaux des utilisateurs et permettent de valider la valeur du produit.

| **Fonctionnalité** | **Description** | **Persona concerné** | **Valeur utilisateur** | **Complexité** |
| :-: | :-: | :-: | :-: | :-: |
| **Inscription et authentification** | Création de compte, connexion/déconnexion, réinitialisation du mot de passe. | Tous | Accès sécurisé à la plateforme. | ⭐⭐ (2) |
| **Personnalisation du profil** | Saisie des informations de base (nom, niveau d’études, objectifs). | Tous | Adaptation de l’expérience utilisateur. | ⭐ (1) |
| **Tableau de bord centralisé** | Vue d’ensemble des tâches, échéances, progrès et notifications. | Tous | Centralisation des informations pour une gestion efficace. | ⭐⭐⭐ (3) |
| **Calendrier intégré** | Gestion des cours, examens, révisions et tâches avec synchronisation (Google Calendar, etc.). | Lucas, Antoine, Marie | Visualisation claire des échéances et organisation du temps. | ⭐⭐⭐ (3) |
| **Gestion des tâches** | Création, modification, suppression et suivi des tâches (devoirs, révisions). | Lucas, Antoine, Marie | Priorisation et suivi des tâches pour éviter les oublis. | ⭐⭐ (2) |
| **Gestion des notes** | Intégration de documents (PDF, liens, fiches de révision) et organisation par matière. | Lucas, Marie | Centralisation des ressources pour un accès rapide. | ⭐⭐ (2) |
| **Groupes collaboratifs** | Création et gestion de groupes pour le partage de ressources et l’organisation de sessions. | Lucas, Antoine | Collaboration efficace entre étudiants. | ⭐⭐⭐⭐ (4) |
| **Ressources personnalisées** | Accès à des quiz, fiches et vidéos adaptés au niveau et aux besoins de l’étudiant. | Lucas, Marie | Apprentissage ciblé et efficace. | ⭐⭐⭐ (3) |



## 3.2. Fonctionnalités Importantes (Améliorations significatives)

Les fonctionnalités **Importantes** apportent une **valeur significative** au produit et améliorent l’expérience utilisateur. Elles sont prioritaires après le MVP.

| **Fonctionnalité** | **Description** | **Persona concerné** | **Valeur utilisateur** | **Complexité** |
| :-: | :-: | :-: | :-: | :-: |
| **Chatbot IA** | Assistant pour poser des questions, obtenir des explications ou des conseils personnalisés. | Lucas, Marie | Accès immédiat à de l’aide et des réponses adaptées. | ⭐⭐⭐⭐⭐ (5) |
| **Suivi des progrès** | Tableau de bord pour visualiser les avancées, les lacunes et les performances par matière. | Lucas, Antoine, Jean-Luc | Motivation et auto-évaluation pour un apprentissage efficace. | ⭐⭐⭐ (3) |
| **Statistiques et analyses** | Génération de rapports détaillés sur les performances et les habitudes de travail. | Jean-Luc, Lucas | Identification des points forts et des axes d’amélioration. | ⭐⭐⭐⭐ (4) |
| **Planification intelligente** | Génération automatique d’un planning adapté aux objectifs, échéances et lacunes de l’étudiant. | Lucas, Marie | Optimisation du temps et réduction du stress. | ⭐⭐⭐⭐ (4) |
| **Rappels intelligents** | Notifications pour les tâches/révisions, basées sur les progrès et les échéances. | Tous | Régularité et réduction de la procrastination. | ⭐⭐ (2) |
| **Génération de quiz/exercices** | Création automatique de quiz et exercices adaptés au niveau et aux lacunes de l’étudiant. | Lucas, Marie, Jean-Luc | Apprentissage actif et ciblé. | ⭐⭐⭐ (3) |
| **Synchronisation avec outils externes** | Intégration avec Google Calendar, Notion, etc. pour centraliser les données. | Lucas, Antoine | Gain de temps et évite la double saisie. | ⭐⭐⭐ (3) |



## 3.3. Fonctionnalités Nice-to-Have (Valeur future)

Les fonctionnalités **Nice-to-Have** ajoutent de la **valeur à long terme** mais ne sont pas prioritaires pour le MVP ou les premières versions.

| **Fonctionnalité** | **Description** | **Persona concerné** | **Valeur utilisateur** | **Complexité** |
| :-: | :-: | :-: | :-: | :-: |
| **Groupes d’entraide** | Espaces dédiés pour échanger avec d’autres étudiants en reconversion ou en alternance. | Marie, Antoine | Soutien mutuel et partage d’expériences. | ⭐⭐ (2) |
| **Intégrations externes** | Connexion avec Slack, GitHub, Moodle, etc. pour une expérience unifiée. | Antoine, Jean-Luc | Fluidité dans l’utilisation des outils professionnels et académiques. | ⭐⭐⭐⭐ (4) |
| **Éditeur de cours** | Outil pour les professeurs afin de créer et partager des supports pédagogiques. | Jean-Luc | Personnalisation des cours et enrichissement des ressources. | ⭐⭐⭐ (3) |
| **Automatisation des corrections** | Correction automatique des quiz et exercices avec feedbacks détaillés. | Jean-Luc | Gain de temps et réduction des tâches administratives. | ⭐⭐⭐⭐ (4) |
| **Évaluation par les pairs** | Système permettant aux étudiants de noter les contributions des membres de leur groupe. | Lucas, Antoine | Encouragement de la collaboration et de l’entraide. | ⭐⭐⭐ (3) |
| **Notifications motivantes** | Envoi de messages d’encouragement et de rappels pour maintenir la motivation. | Marie | Régularité et persévérance dans les révisions. | ⭐ (1) |
| **Prompts mémorisés** | Prompts prédéfinis pour interagir rapidement avec le chatbot IA. | Tous | Gain de temps et interactions fluides. | ⭐⭐ (2) |
| **Tableau blanc collaboratif** | Outil pour résoudre des exercices ou brainstormer en temps réel avec d’autres étudiants. | Lucas, Antoine | Collaboration visuelle et interactive. | ⭐⭐⭐⭐ (4) |
| **Visioconférence intégrée** | Organisation de sessions de travail en ligne directement depuis la plateforme. | Lucas, Antoine | Facilitation des révisions en groupe. | ⭐⭐⭐⭐ (4) |



## 3.4. Priorisation et Backlog

Pour structurer le développement, les fonctionnalités sont organisées en **3 colonnes** : **Must Have (Core)**, **Should Have (Importantes)**, et **Could Have (Nice-to-Have)**.

| **Must Have (Core - V1)** | **Should Have (Importantes - V1.1)** | **Could Have (Nice-to-Have - V2+)** |
| :-: | :-: | :-: |
| Inscription et authentification | Chatbot IA | Groupes d’entraide |
| Personnalisation du profil | Suivi des progrès | Intégrations externes (Slack, GitHub) |
| Tableau de bord centralisé | Statistiques et analyses | Éditeur de cours |
| Calendrier intégré | Planification intelligente | Automatisation des corrections |
| Gestion des tâches | Rappels intelligents | Évaluation par les pairs |
| Gestion des notes | Génération de quiz/exercices | Notifications motivantes |
| Groupes collaboratifs | Synchronisation avec outils externes | Prompts mémorisés |
| Ressources personnalisées |  | Tableau blanc collaboratif |
|  |  | Visioconférence intégrée |



## 3.5. Analyse de complexité

L’analyse de complexité permet d’estimer les **ressources nécessaires** (temps, compétences, coûts) pour implémenter chaque fonctionnalité.

| **Complexité** | **Description** | **Fonctionnalités associées** | **Risques/Defis** |
| :-: | :-: | :-: | :-: |
| ⭐ (1) | Simple à implémenter, peu de dépendances techniques. | Inscription, personnalisation du profil, notifications motivantes, prompts mémorisés. | Aucun risque majeur. |
| ⭐⭐ (2) | Complexité modérée, nécessite des intégrations basiques. | Gestion des tâches, gestion des notes, groupes d’entraide, rappels intelligents. | Synchronisation des données entre modules. |
| ⭐⭐⭐ (3) | Complexité élevée, nécessite des algorithmes ou des intégrations avancées. | Tableau de bord centralisé, suivi des progrès, génération de quiz, éditeur de cours. | Performance et scalabilité à surveiller. |
| ⭐⭐⭐⭐ (4) | Très complexe, nécessite des ressources techniques importantes. | Groupes collaboratifs, planification intelligente, automatisation des corrections, tableau blanc collaboratif. | Intégration avec l’IA et gestion des conflits de données. |
| ⭐⭐⭐⭐⭐ (5) | Extrêmement complexe, dépendances multiples et technologies avancées. | Chatbot IA, visioconférence intégrée, intégrations externes (Slack, GitHub). | Coûts élevés (API IA), latence, sécurité des données. |



**Légende** :

- **⭐** : Simple (1-2 semaines de développement).

- **⭐⭐⭐** : Modéré (3-6 semaines).

- **⭐⭐⭐⭐⭐** : Complexe (6+ semaines ou ressources externes nécessaires).


# 4. Architecture de l’application et parcours utilisateurs


## 4.1. Introduction

Ce chapitre décrit l’**architecture globale** de StudyFlow AI, incluant :

- La **structure des pages** (sitemap).

- Les **parcours utilisateurs** (user flows).

- La **navigation** (sidebar, top nav, bottom nav).

- Les **composants techniques** et leur intégration.

L’objectif est de garantir une **expérience utilisateur fluide**, une **accessibilité optimale** (≤ 3 clics pour toute fonctionnalité), et une **scalabilité** pour les futures évolutions.


## 4.2. Sitemap (Structure des pages)

Le **sitemap** de StudyFlow AI est organisé en **4 catégories principales** :

1. **Pages publiques** (avant connexion).

2. **Espace connecté** (après connexion).

3. **Paramètres** (personnalisation utilisateur).

4. **Administration** (gestion des utilisateurs et facturation).


### 4.2.1. Pages publiques (avant connexion)

| **Page** | **Route URL** | **Description** |
| :-: | :-: | :-: |
| Landing Page | `/` | Page d’accueil avec CTA (inscription/connexion). |
| Inscription | `/register` | Formulaire d’inscription. |
| Connexion | `/login` | Formulaire de connexion. |
| Mot de passe oublié | `/forgot-password` | Réinitialisation du mot de passe. |
| CGU/CGV | `/terms` | Conditions Générales d’Utilisation. |
| Politique de confidentialité | `/privacy` | Informations RGPD. |
| 404 | `/404` | Page d’erreur personnalisée. |
| 500 | `/500` | Erreur serveur. |


![Identification / Connexion](Authentication%20Identification.png)


### 4.2.2. Espace connecté (après connexion)

| **Page (Niveau 1)** | **Route URL** | **Sous-pages (Niveau 2)** | **Route URL** | **Sous-sous-pages (Niveau 3)** | **Route URL** | **Description** |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **Tableau de bord** | `/dashboard` | - | - | - | - | Vue centrale avec résumé des tâches, échéances, progrès et notifications. |
| **Calendrier** | `/dashboard/calendrier` | Ajouter un événement | `/dashboard/calendrier/ajouter` | - | - | Visualisation/édition des événements. |
|  |  | Synchroniser avec Google Calendar | `/dashboard/calendrier/sync` | - | - | Paramétrage de la synchronisation. |
| **Tâches** | `/dashboard/taches` | Créer une tâche | `/dashboard/taches/ajouter` | Détails d’une tâche | `/dashboard/taches/:id` | Vue détaillée + marquage comme terminée. |
| **Plan de révision** | `/dashboard/plan-revision` | Valider/Modifier le plan | `/dashboard/plan-revision/modifier` | - | - | Plan généré par l’IA. |
| **Groupes collaboratifs** | `/dashboard/groupes` | Créer un groupe | `/dashboard/groupes/ajouter` | Détails d’un groupe | `/dashboard/groupes/:id` | Ressources partagées, membres, chat du groupe. |
| **Ressources** | `/dashboard/ressources` | Ajouter une ressource | `/dashboard/ressources/ajouter` | Noter une ressource | `/dashboard/ressources/:id/notation` | Upload de fichiers/liens. |
| **Notifications** | `/dashboard/notifications` | - | - | - | - | Hub centralisé (alertes tâches, messages de groupe, rappels). |
| **Chatbot IA** | Widget flottant | - | - | - | - | Accessible depuis n’importe quelle page de l’espace connecté. |



### 4.2.3. Paramètres

| **Page** | **Route URL** | **Description** |
| :-: | :-: | :-: |
| Profil | `/settings/profile` | Visualisation/édition des infos personnelles. |
| Préférences | `/settings/preferences` | Langue, thème, notifications. |
| Sécurité | `/settings/security` | Mot de passe, 2FA, historique des connexions. |
| Abonnement | `/settings/subscription` | Gestion de l’abonnement. |



### 4.2.4. Administration

| **Page** | **Route URL** | **Description** |
| :-: | :-: | :-: |
| Gestion des utilisateurs | `/admin/users` | Liste des utilisateurs (admins). |
| Détails utilisateur | `/admin/users/:id` | Visualisation/modification des infos utilisateur. |
| Facturation | `/admin/billing` | Suivi des paiements, abonnements. |



**Schéma visuel du sitemap** :

![Sitemap](Graph-SiteMap.png)


## 4.3. Parcours utilisateurs (User Flows)

Les **user flows** détaillent les **étapes séquentielles** pour accomplir les tâches principales dans StudyFlow AI. Chaque flow inclut :

- Le **point d’entrée**.

- Les **étapes** avec les écrans traversés.

- Les **points de décision** (succès et cas d’erreur).

- Le **point de sortie** et la confirmation.


### 4.3.1. Flow 1 : Connexion / Identification de l’utilisateur

![Connexion](Graph-ParcoursUtilisateurs.png)


### 4.3.2. Flow 2 : Nouvelle tâche et planification

![Connexion](Graph-NouvelleTachePlanning.png)


### 4.3.3. Flow 3 : Gestion des ressources

![Connexion](Graph-GestionRessources.png)


## 4.4. Structure de navigation

La navigation de StudyFlow AI est conçue pour être **intuitive**, **accessible** et **adaptée aux besoins des étudiants multitâches**.


### 4.4.1. Menu principal (Sidebar)

**Justification** :

- Accès rapide aux fonctionnalités principales (tâches, calendrier, ressources).

- Gain de place sur les écrans **mobile** et **desktop**.

- Adapté aux **personas** : les étudiants multitâches ont besoin d’une navigation **persistante** et **intuitive**.

**Éléments du menu (Sidebar)** :

- **Accueil** → `/dashboard`

- **Calendrier** → `/dashboard/calendrier`

- **Tâches** → `/dashboard/taches`

- **Ressources** → `/dashboard/ressources`

- **Groupes** → `/dashboard/groupes`

- **Chatbot IA** (Widget flottant, toujours visible en bas à droite).

- **Notifications** → `/dashboard/notifications` (icône en haut à droite).

- **Paramètres** → Menu déroulant :

  - Profil → `/settings/profile`

  - Préférences → `/settings/preferences`

  - Sécurité → `/settings/security`

  - Abonnement → `/settings/subscription`


### 4.4.2. Éléments toujours visibles vs contextuels

| **Type** | **Éléments** | **Position** | **Justification** |
| :-: | :-: | :-: | :-: |
| Toujours visibles | Logo (StudyFlow AI) | Top-left (header) | Identification immédiate de l’application. |
|  | Barre de recherche | Top (header) | Accès rapide aux ressources/tâches sans naviguer. |
|  | Icône Notifications (🔔) | Top-right (header) | Alertes en temps réel (tâches, messages de groupe). |
|  | Chatbot IA (Widget) | Bas à droite (flottant) | Accessibilité immédiate depuis n’importe quelle page. |
| Contextuels | Bouton "Ajouter" | Dans chaque section | Ajout rapide de tâches, ressources ou événements. |
|  | Breadcrumbs | Haut de page | Indication de la hiérarchie (ex : *Accueil \> Tâches \> Détails*). |



### 4.4.3. Patterns de navigation

#### Desktop (Sidebar + Top Nav)

- **Sidebar** (à gauche) :

  - Menu principal (Accueil, Calendrier, Tâches, etc.).

  - **Collapsible** pour gagner de la place.

  - Icônes + texte pour une identification claire.

- **Top Navigation Bar** (en haut) :

  - Logo + barre de recherche.

  - Icônes **Notifications (🔔)** et **Profil (👤)**.

  - Bouton **"Panneau Admin"** (si admin).

#### Mobile (Bottom Nav + Hamburger Menu)

- **Bottom Navigation Bar** (en bas) :

  - 4 icônes principales :

    - **Accueil** (`/dashboard`)

    - **Calendrier** (`/dashboard/calendrier`)

    - **Tâches** (`/dashboard/taches`)

    - **Ressources** (`/dashboard/ressources`)

- **Hamburger Menu (☰)** :

  - Accès aux autres pages (**Groupes**, **Paramètres**, **Administration**).

  - **Chatbot IA** reste en widget flottant.

- **Breadcrumb** :

  - Affiché en haut de page pour indiquer la hiérarchie (ex : *Accueil \> Tâches \> Détails*).


## 4.5. Justification des choix pour le persona primaire (Étudiant)

| **Choix** | **Pourquoi ?** |
| :-: | :-: |
| **Sidebar persistante** | Les étudiants ont besoin d’un accès **rapide** et **permanent** aux fonctionnalités principales. |
| **Bottom Nav pour mobile** | Les étudiants utilisent souvent leur mobile pour des **actions rapides** (ex : vérifier une tâche). |
| **Chatbot IA en widget flottant** | Accessibilité immédiate pour poser des questions **sans quitter la page en cours**. |
| **Breadcrumbs** | Aide à comprendre la **hiérarchie** et à naviguer facilement. |
| **Barre de recherche globale** | Permet de trouver rapidement une ressource ou une tâche **sans naviguer**. |
| **Notifications centralisées** | Les étudiants doivent être **alertés en temps réel** des échéances et messages. |



## 4.6. Audit de l’architecture

L’audit a permis d’identifier les **points forts** et les **axes d’amélioration** de l’architecture actuelle.


### 4.6.1. Points forts

✅ **Hiérarchie claire** : Toutes les fonctionnalités MVP sont accessibles en **≤ 3 clics**.

✅ **Navigation intuitive** : Sidebar + Bottom Nav pour mobile = **expérience fluide**.

✅ **Intégration du chatbot IA** : Widget flottant = **accessibilité maximale**.

✅ **Gestion des erreurs** : Pages 404/500 et messages d’erreur **personnalisés**.


### 4.6.2. Axes d’amélioration

| **Problème identifié** | **Solution proposée** | **Priorité** |
| :-: | :-: | :-: |
| Pages du sitemap inaccessibles depuis la navigation (ex : `/admin/billing`). | Ajouter un lien dans le menu **Paramètres** pour les admins. | Haute |
| Flows avec \> 7 étapes (ex : synchronisation Google Calendar). | Simplifier en **automatisant** la synchronisation (ex : bouton "Synchroniser tout"). | Moyenne |
| Cas d’erreur non gérés (ex : échec de synchronisation). | Ajouter des **messages d’erreur clairs** et des **solutions** (ex : "Réessayer" ou "Contacter le support"). | Haute |
| Incohérences entre flows et fonctionnalités MVP. | Vérifier que toutes les fonctionnalités MVP sont **couvertes par un flow**. | Haute |



# 5. Modèle conceptuel de données


## 5.1. Introduction

Ce chapitre présente le **modèle conceptuel de données (MCD)** de StudyFlow AI, conçu pour structurer les informations essentielles de l’application. Le MCD identifie les **entités**, leurs **relations**, et les **contraintes** associées, afin de servir de base pour la conception de la base de données.

L’objectif est de garantir :

- Une **cohérence** entre les fonctionnalités et les données stockées.

- Une **scalabilité** pour les futures évolutions (ex : ajout de nouvelles fonctionnalités IA).

- Une **optimisation** des requêtes et des performances.


## 5.2. Entités principales et relations

Le MCD de StudyFlow AI repose sur **10 entités principales**, organisées pour couvrir les besoins du MVP et des versions futures.

| **Entité** | **Description** | **Relations** | **Exemple de champs** |
| :-: | :-: | :-: | :-: |
| **Utilisateur** | Représente un utilisateur de la plateforme (étudiant, professeur, admin). | 1:N avec Tâche, Ressource, Groupe, Quiz, Progrès. | `id`, `nom`, `email`, `mot\_de\_passe`, `role`, `date\_inscription`, `dernière\_connexion`, `statut\_compte` |
| **Profil** | Informations complémentaires sur l’utilisateur (préférences, objectifs). | 1:1 avec Utilisateur. | `id\_utilisateur`, `niveau\_études`, `objectifs`, `préférences\_thème`, `langue` |
| **Tâche** | Une tâche à accomplir (devoir, révision, projet). | N:1 avec Utilisateur (créateur), N:M avec Groupe (partage). | `id`, `id\_utilisateur`, `titre`, `description`, `date\_échéance`, `statut`, `priorité` |
| **Échéance** | Une échéance liée à une tâche ou un événement (ex : examen, rendu de devoir). | 1:1 avec Tâche ou Événement. | `id`, `id\_tâche`, `date`, `type` (examen/devoir), `description` |
| **Événement** | Un événement dans le calendrier (cours, réunion, session de révision). | 1:N avec Utilisateur (participants), 1:1 avec Échéance. | `id`, `titre`, `date\_debut`, `date\_fin`, `lieu`, `type` (cours/réunion/autre) |
| **Ressource** | Une ressource partagée (fiche, vidéo, lien, quiz). | N:1 avec Utilisateur (créateur), N:M avec Groupe (partage), 1:N avec Note. | `id`, `id\_utilisateur`, `titre`, `type` (fiche/vidéo/lien), `url`, `date\_ajout`, `notation\_moyenne` |
| **Groupe** | Un groupe collaboratif (révisions, projets). | N:M avec Utilisateur (membres), 1:N avec Tâche/Ressource (partage). | `id`, `nom`, `description`, `date\_création`, `id\_créateur`, `statut` (public/privé) |
| **Quiz** | Un quiz généré par l’IA ou créé manuellement. | 1:N avec Question\_Quiz, N:1 avec Utilisateur (créateur). | `id`, `id\_utilisateur`, `titre`, `description`, `date\_création`, `difficulté` |
| **Question\_Quiz** | Une question dans un quiz. | N:1 avec Quiz, 1:N avec Réponse\_Quiz. | `id`, `id\_quiz`, `énoncé`, `type` (QCM/vrai-faux/réponse courte), `points` |
| **Réponse\_Quiz** | Une réponse à une question de quiz. | N:1 avec Question\_Quiz, 1:1 avec Utilisateur. | `id`, `id\_question\_quiz`, `id\_utilisateur`, `réponse`, `date\_soumission`, `score` |
| **Progrès** | Suivi des progrès de l’utilisateur (ex : scores, temps passé). | 1:1 avec Utilisateur, N:1 avec Quiz. | `id\_utilisateur`, `id\_quiz`, `score`, `temps\_passé`, `date`, `matière` |
| **Notification** | Une notification envoyée à l’utilisateur (rappel, message de groupe). | N:1 avec Utilisateur. | `id`, `id\_utilisateur`, `titre`, `message`, `date\_envoi`, `statut` (lue/non lue), `type` |
| **Salle** | Une salle virtuelle pour les sessions de travail en groupe. | 1:N avec Séance. | `id`, `nom`, `description`, `capacité`, `id\_créateur` |
| **Séance** | Une session de travail (ex : révision en groupe, cours en ligne). | N:1 avec Salle, N:M avec Utilisateur (participants). | `id`, `id\_salle`, `titre`, `date\_debut`, `date\_fin`, `statut` (planifiée/en cours/terminée) |
| **Demande\_Reset\_MotDePasse** | Une demande de réinitialisation de mot de passe. | 1:1 avec Utilisateur. | `id`, `id\_utilisateur`, `jeton`, `date\_demande`, `statut` (valide/expiré) |



**Schéma des relations entre les entités** :

 ![Classe relations](Graph-Classe.png)


## 5.3. Vérification de cohérence du modèle

Une **vérification de cohérence** a été réalisée pour identifier les **champs manquants**, les **types à optimiser**, et les **valeurs par défaut** à ajouter.

| **Catégorie** | **Problème identifié** | **Solution proposée** | **Impact** |
| :-: | :-: | :-: | :-: |
| **Champs manquants** | Absence de `dernière\_connexion` pour suivre l’activité des utilisateurs. | Ajouter le champ `dernière\_connexion` (type `TIMESTAMP WITH TIME ZONE`) dans la table `Utilisateur`. | Meilleure analyse de l’activité utilisateur. |
|  | Absence de `statut\_compte` pour gérer les comptes actifs/inactifs. | Ajouter le champ `statut\_compte` (type `ENUM : \['actif', 'inactif', 'suspendu'\]`) dans `Utilisateur`. | Meilleure gestion des comptes. |
| **Types à optimiser** | Les dates sont stockées en `DATE` au lieu de `TIMESTAMP WITH TIME ZONE`. | Remplacer par `TIMESTAMP WITH TIME ZONE` pour toutes les dates (ex : `date\_échéance`, `date\_debut`). | Précision et gestion des fuseaux horaires. |
| **Valeurs par défaut** | Aucune valeur par défaut pour `statut\_compte`. | Définir `statut\_compte = 'actif'` par défaut. | Cohérence des données dès la création. |
| **Redondances** | Aucune redondance détectée. | - | - |



## 5.4. Croisement de cohérence et corrections

Un **croisement de cohérence** a révélé des **incohérences** et des **manquements** dans le modèle initial, nécessitant des corrections pour le MVP.

| **Catégorie** | **Problème identifié** | **Solution proposée** | **Impact** |
| :-: | :-: | :-: | :-: |
| **Tables manquantes** | Absence de table `Utilisateur\_Cours` pour gérer les relations N:N entre utilisateurs et cours. | Créer une table `Utilisateur\_Cours` avec les champs : `id\_utilisateur`, `id\_cours`, `date\_inscription`. | Permet de suivre les inscriptions aux cours. |
| **Champs à ajouter** | Absence de `email\_verifié` pour valider les emails des utilisateurs. | Ajouter le champ `email\_verifié` (type `BOOLEAN`, valeur par défaut `FALSE`) dans `Utilisateur`. | Sécurité et validation des comptes. |
|  | Absence de `jeton\_reinitialisation` pour la réinitialisation des mots de passe. | Ajouter le champ `jeton\_reinitialisation` (type `UUID`) dans `Demande\_Reset\_MotDePasse`. | Sécurité des demandes de réinitialisation. |
| **Contraintes à renforcer** | Synchronisation manuelle entre `Tâche` et `Événement`. | Ajouter un **trigger** pour synchroniser automatiquement les dates entre `Tâche` et `Événement`. | Évite les incohérences de dates. |
|  | Pas de protection du créateur de groupe (un membre peut supprimer le groupe). | Ajouter une **contrainte** : seul le `id\_créateur` peut supprimer un `Groupe`. | Sécurité et intégrité des données. |
| **Risques de duplication** | Duplication possible des dates entre `Tâche` et `Événement`. | Utiliser des **triggers** pour synchroniser les dates. | Cohérence des données. |
|  | Duplication des notifications (ex : rappel de tâche + notification de groupe). | Ajouter une **vue SQL** pour regrouper les notifications similaires. | Évite la surcharge de notifications. |



## 5.5. Script SQL de création de la base de données

Le **script SQL** pour Supabase (PostgreSQL) inclut :

- Les **extensions** nécessaires (ex : `uuid-ossp` pour générer des UUID).

- Les **énumérations** pour les champs à valeurs prédéfinies (ex : `role`, `statut\_compte`).

- Les **tables** avec leurs champs et contraintes.

- Les **triggers** pour la synchronisation et la sécurité.

- Les **index** pour l’optimisation des requêtes.

- Les **vues SQL** pour le tableau de bord.

- Les **politiques RLS** (Row-Level Security) pour la sécurité.


### 5.5.1. Extensions et énumérations

```
-- Extensions  
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";  
CREATE EXTENSION IF NOT EXISTS "pg\_trgm";  
  
-- Énumérations  
CREATE TYPE role\_enum AS ENUM ('étudiant', 'professeur', 'admin');  
CREATE TYPE statut\_compte\_enum AS ENUM ('actif', 'inactif', 'suspendu');  
CREATE TYPE type\_ressource\_enum AS ENUM ('fiche', 'vidéo', 'lien', 'quiz', 'autre');  
CREATE TYPE type\_tâche\_enum AS ENUM ('devoir', 'révision', 'projet', 'autre');  
CREATE TYPE statut\_tâche\_enum AS ENUM ('à faire', 'en cours', 'terminée', 'archivée');  
CREATE TYPE priorité\_enum AS ENUM ('basse', 'moyenne', 'haute', 'urgente');  
CREATE TYPE type\_événement\_enum AS ENUM ('cours', 'réunion', 'examen', 'autre');  
CREATE TYPE type\_notification\_enum AS ENUM ('rappel', 'message', 'alerte', 'autre');  
CREATE TYPE statut\_groupe\_enum AS ENUM ('public', 'privé', 'archivé');  
CREATE TYPE difficulté\_quiz\_enum AS ENUM ('facile', 'moyenne', 'difficile');  
CREATE TYPE type\_question\_enum AS ENUM ('QCM', 'vrai-faux', 'réponse courte', 'réponse longue');  
CREATE TYPE statut\_séance\_enum AS ENUM ('planifiée', 'en cours', 'terminée', 'annulée');
```


### 5.5.2. Tables principales

```
-- Table Utilisateur  
CREATE TABLE Utilisateur (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    nom VARCHAR(100) NOT NULL,  
    email VARCHAR(255) UNIQUE NOT NULL,  
    mot\_de\_passe VARCHAR(255) NOT NULL,  
    role role\_enum NOT NULL DEFAULT 'étudiant',  
    date\_inscription TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    dernière\_connexion TIMESTAMP WITH TIME ZONE,  
    statut\_compte statut\_compte\_enum NOT NULL DEFAULT 'actif',  
    email\_verifié BOOLEAN NOT NULL DEFAULT FALSE  
);  
  
-- Table Profil  
CREATE TABLE Profil (  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    niveau\_études VARCHAR(100),  
    objectifs TEXT,  
    préférences\_thème VARCHAR(50) DEFAULT 'clair',  
    langue VARCHAR(50) DEFAULT 'fr',  
    PRIMARY KEY (id\_utilisateur)  
);  
  
-- Table Tâche  
CREATE TABLE Tâche (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    titre VARCHAR(255) NOT NULL,  
    description TEXT,  
    date\_échéance TIMESTAMP WITH TIME ZONE,  
    statut statut\_tâche\_enum NOT NULL DEFAULT 'à faire',  
    priorité priorité\_enum NOT NULL DEFAULT 'moyenne',  
    type type\_tâche\_enum NOT NULL DEFAULT 'révision',  
    date\_création TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW()  
);  
  
-- Table Échéance  
CREATE TABLE Échéance (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_tâche UUID REFERENCES Tâche(id) ON DELETE CASCADE,  
    date TIMESTAMP WITH TIME ZONE NOT NULL,  
    type VARCHAR(50) NOT NULL,  
    description TEXT  
);  
  
-- Table Événement  
CREATE TABLE Événement (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    titre VARCHAR(255) NOT NULL,  
    date\_debut TIMESTAMP WITH TIME ZONE NOT NULL,  
    date\_fin TIMESTAMP WITH TIME ZONE NOT NULL,  
    lieu VARCHAR(255),  
    type type\_événement\_enum NOT NULL DEFAULT 'cours',  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE  
);  
  
-- Table Ressource  
CREATE TABLE Ressource (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    titre VARCHAR(255) NOT NULL,  
    type type\_ressource\_enum NOT NULL DEFAULT 'fiche',  
    url TEXT,  
    contenu TEXT,  
    date\_ajout TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    notation\_moyenne DECIMAL(3,2) DEFAULT 0.00  
);  
  
-- Table Groupe  
CREATE TABLE Groupe (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    nom VARCHAR(255) NOT NULL,  
    description TEXT,  
    date\_création TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    id\_créateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    statut statut\_groupe\_enum NOT NULL DEFAULT 'public'  
);  
  
-- Table Utilisateur\_Groupe (relation N:N)  
CREATE TABLE Utilisateur\_Groupe (  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    id\_groupe UUID REFERENCES Groupe(id) ON DELETE CASCADE,  
    date\_adhésion TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    PRIMARY KEY (id\_utilisateur, id\_groupe)  
);  
  
-- Table Quiz  
CREATE TABLE Quiz (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    titre VARCHAR(255) NOT NULL,  
    description TEXT,  
    date\_création TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    difficulté difficulté\_quiz\_enum NOT NULL DEFAULT 'moyenne'  
);  
  
-- Table Question\_Quiz  
CREATE TABLE Question\_Quiz (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_quiz UUID REFERENCES Quiz(id) ON DELETE CASCADE,  
    énoncé TEXT NOT NULL,  
    type type\_question\_enum NOT NULL DEFAULT 'QCM',  
    points INTEGER NOT NULL DEFAULT 1  
);  
  
-- Table Réponse\_Quiz  
CREATE TABLE Réponse\_Quiz (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_question\_quiz UUID REFERENCES Question\_Quiz(id) ON DELETE CASCADE,  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    réponse TEXT,  
    date\_soumission TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    score INTEGER  
);  
  
-- Table Progrès  
CREATE TABLE Progrès (  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    id\_quiz UUID REFERENCES Quiz(id) ON DELETE CASCADE,  
    score INTEGER NOT NULL,  
    temps\_passé INTEGER NOT NULL, -- en secondes  
    date TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    matière VARCHAR(100),  
    PRIMARY KEY (id\_utilisateur, id\_quiz, date)  
);  
  
-- Table Notification  
CREATE TABLE Notification (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    titre VARCHAR(255) NOT NULL,  
    message TEXT NOT NULL,  
    date\_envoi TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    statut BOOLEAN NOT NULL DEFAULT FALSE, -- FALSE = non lue, TRUE = lue  
    type type\_notification\_enum NOT NULL DEFAULT 'rappel'  
);  
  
-- Table Salle  
CREATE TABLE Salle (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    nom VARCHAR(255) NOT NULL,  
    description TEXT,  
    capacité INTEGER NOT NULL DEFAULT 10,  
    id\_créateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE  
);  
  
-- Table Séance  
CREATE TABLE Séance (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_salle UUID REFERENCES Salle(id) ON DELETE CASCADE,  
    titre VARCHAR(255) NOT NULL,  
    date\_debut TIMESTAMP WITH TIME ZONE NOT NULL,  
    date\_fin TIMESTAMP WITH TIME ZONE NOT NULL,  
    statut statut\_séance\_enum NOT NULL DEFAULT 'planifiée'  
);  
  
-- Table Utilisateur\_Séance (relation N:N)  
CREATE TABLE Utilisateur\_Séance (  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    id\_séance UUID REFERENCES Séance(id) ON DELETE CASCADE,  
    date\_participation TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    PRIMARY KEY (id\_utilisateur, id\_séance)  
);  
  
-- Table Demande\_Reset\_MotDePasse  
CREATE TABLE Demande\_Reset\_MotDePasse (  
    id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4(),  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    jeton UUID NOT NULL DEFAULT uuid\_generate\_v4(),  
    date\_demande TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    statut VARCHAR(50) NOT NULL DEFAULT 'valide' -- 'valide' ou 'expiré'  
);  
  
-- Table Utilisateur\_Cours (relation N:N)  
CREATE TABLE Utilisateur\_Cours (  
    id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE,  
    id\_cours UUID NOT NULL,  
    date\_inscription TIMESTAMP WITH TIME ZONE NOT NULL DEFAULT NOW(),  
    PRIMARY KEY (id\_utilisateur, id\_cours)  
);
```


### 5.5.3. Triggers pour la synchronisation et la sécurité

```
-- Trigger pour synchroniser les dates entre Tâche et Événement  
CREATE OR REPLACE FUNCTION synchroniser\_tâche\_événement()  
RETURNS TRIGGER AS $$  
BEGIN  
    IF TG\_OP = 'INSERT' OR TG\_OP = 'UPDATE' THEN  
        IF NEW.date\_échéance IS NOT NULL THEN  
            INSERT INTO Événement (titre, date\_debut, date\_fin, type, id\_utilisateur)  
            VALUES (NEW.titre, NEW.date\_échéance, NEW.date\_échéance, 'révision', NEW.id\_utilisateur)  
            ON CONFLICT (id) DO UPDATE  
            SET date\_debut = EXCLUDED.date\_debut,  
                date\_fin = EXCLUDED.date\_fin;  
        END IF;  
    END IF;  
    RETURN NEW;  
END;  
$$ LANGUAGE plpgsql;  
  
CREATE TRIGGER trigger\_synchroniser\_tâche\_événement  
AFTER INSERT OR UPDATE ON Tâche  
FOR EACH ROW  
EXECUTE FUNCTION synchroniser\_tâche\_événement();  
  
-- Trigger pour protéger le créateur de groupe  
CREATE OR REPLACE FUNCTION protéger\_créateur\_groupe()  
RETURNS TRIGGER AS $$  
BEGIN  
    IF TG\_OP = 'DELETE' THEN  
        IF OLD.id\_créateur = current\_setting('app.current\_user\_id')::UUID THEN  
            RAISE EXCEPTION 'Seul le créateur peut supprimer ce groupe.';  
        END IF;  
    END IF;  
    RETURN OLD;  
END;  
$$ LANGUAGE plpgsql;  
  
CREATE TRIGGER trigger\_protéger\_créateur\_groupe  
BEFORE DELETE ON Groupe  
FOR EACH ROW  
EXECUTE FUNCTION protéger\_créateur\_groupe();
```


### 5.5.4. Index pour l’optimisation

```
-- Index pour accélérer les requêtes sur les tâches  
CREATE INDEX idx\_tâche\_id\_utilisateur ON Tâche(id\_utilisateur);  
CREATE INDEX idx\_tâche\_date\_échéance ON Tâche(date\_échéance);  
CREATE INDEX idx\_tâche\_statut ON Tâche(statut);  
  
-- Index pour accélérer les requêtes sur les ressources  
CREATE INDEX idx\_ressource\_id\_utilisateur ON Ressource(id\_utilisateur);  
CREATE INDEX idx\_ressource\_type ON Ressource(type);  
  
-- Index pour accélérer les requêtes sur les groupes  
CREATE INDEX idx\_groupe\_id\_créateur ON Groupe(id\_créateur);  
CREATE INDEX idx\_utilisateur\_groupe\_id\_utilisateur ON Utilisateur\_Groupe(id\_utilisateur);  
CREATE INDEX idx\_utilisateur\_groupe\_id\_groupe ON Utilisateur\_Groupe(id\_groupe);  
  
-- Index pour accélérer les requêtes sur les quiz  
CREATE INDEX idx\_quiz\_id\_utilisateur ON Quiz(id\_utilisateur);  
CREATE INDEX idx\_progrès\_id\_utilisateur ON Progrès(id\_utilisateur);
```


### 5.5.5. Vue SQL pour le tableau de bord

```
-- Vue pour le tableau de bord utilisateur  
CREATE VIEW vue\_tableau\_de\_bord AS  
SELECT  
    u.id AS id\_utilisateur,  
    u.nom,  
    u.email,  
    COUNT(t.id) AS nombre\_tâches,  
    COUNT(CASE WHEN t.statut = 'terminée' THEN 1 END) AS tâches\_terminées,  
    COUNT(CASE WHEN t.statut = 'à faire' THEN 1 END) AS tâches\_à\_faire,  
    COUNT(e.id) AS nombre\_événements,  
    COUNT(r.id) AS nombre\_ressources,  
    COUNT(g.id) AS nombre\_groupes,  
    AVG(p.score) AS score\_moyen\_quiz  
FROM Utilisateur u  
LEFT JOIN Tâche t ON u.id = t.id\_utilisateur  
LEFT JOIN Événement e ON u.id = e.id\_utilisateur  
LEFT JOIN Ressource r ON u.id = r.id\_utilisateur  
LEFT JOIN Utilisateur\_Groupe ug ON u.id = ug.id\_utilisateur  
LEFT JOIN Groupe g ON ug.id\_groupe = g.id  
LEFT JOIN Progrès p ON u.id = p.id\_utilisateur  
WHERE u.id = current\_setting('app.current\_user\_id')::UUID  
GROUP BY u.id, u.nom, u.email;
```


### 5.5.6. Politiques RLS (Row-Level Security)

```
-- Politique RLS pour la table Utilisateur  
ALTER TABLE Utilisateur ENABLE ROW LEVEL SECURITY;  
  
CREATE POLICY "Les utilisateurs peuvent voir leur propre profil"  
ON Utilisateur  
FOR SELECT  
USING (id = current\_setting('app.current\_user\_id')::UUID);  
  
CREATE POLICY "Les utilisateurs peuvent mettre à jour leur propre profil"  
ON Utilisateur  
FOR UPDATE  
USING (id = current\_setting('app.current\_user\_id')::UUID);  
  
-- Politique RLS pour la table Tâche  
ALTER TABLE Tâche ENABLE ROW LEVEL SECURITY;  
  
CREATE POLICY "Les utilisateurs peuvent voir leurs propres tâches"  
ON Tâche  
FOR SELECT  
USING (id\_utilisateur = current\_setting('app.current\_user\_id')::UUID);  
  
CREATE POLICY "Les utilisateurs peuvent ajouter leurs propres tâches"  
ON Tâche  
FOR INSERT  
WITH CHECK (id\_utilisateur = current\_setting('app.current\_user\_id')::UUID);  
  
-- Politique RLS pour la table Ressource  
ALTER TABLE Ressource ENABLE ROW LEVEL SECURITY;  
  
CREATE POLICY "Les utilisateurs peuvent voir leurs propres ressources et celles partagées"  
ON Ressource  
FOR SELECT  
USING (  
    id\_utilisateur = current\_setting('app.current\_user\_id')::UUID OR  
    id IN (SELECT id FROM Ressource r JOIN Utilisateur\_Groupe ug ON r.id\_utilisateur = ug.id\_utilisateur WHERE ug.id\_groupe IN (SELECT id\_groupe FROM Utilisateur\_Groupe WHERE id\_utilisateur = current\_setting('app.current\_user\_id')::UUID))  
);
```


## 5.6. Schéma visuel du modèle conceptuel

Voici un **schéma visuel** du modèle conceptuel de données, illustrant les **entités** et leurs **relations** :

![Mcd](Modele.png)


## 5.7. Conventions et bonnes pratiques

Pour garantir la **qualité**, la **sécurité** et la **maintenabilité** de la base de données, les conventions suivantes sont appliquées :

| **Catégorie** | **Convention** | **Exemple** |
| :-: | :-: | :-: |
| **Nommage des tables** | Nom au **singulier**, en **snake\_case**. | `Utilisateur`, `Tâche`, `Ressource`. |
| **Nommage des champs** | Nom en **snake\_case**, avec un préfixe si nécessaire (ex : `id\_` pour les clés étrangères). | `id\_utilisateur`, `date\_échéance`, `statut\_compte`. |
| **Types de données** | Utiliser les types **PostgreSQL** adaptés (ex : `TIMESTAMP WITH TIME ZONE` pour les dates). | `date\_échéance TIMESTAMP WITH TIME ZONE`. |
| **Clés primaires** | Utiliser des **UUID** pour les identifiants uniques. | `id UUID PRIMARY KEY DEFAULT uuid\_generate\_v4()`. |
| **Clés étrangères** | Toujours ajouter `ON DELETE CASCADE` pour éviter les orphelins. | `id\_utilisateur UUID REFERENCES Utilisateur(id) ON DELETE CASCADE`. |
| **Valeurs par défaut** | Définir des valeurs par défaut pour les champs obligatoires. | `statut\_compte statut\_compte\_enum NOT NULL DEFAULT 'actif'`. |
| **Index** | Créer des index pour les champs fréquemment interrogés. | `CREATE INDEX idx\_tâche\_id\_utilisateur ON Tâche(id\_utilisateur)`. |
| **Triggers** | Utiliser des triggers pour automatiser les actions répétitives. | Trigger pour synchroniser `Tâche` et `Événement`. |
| **RLS (Row-Level Security)** | Appliquer des politiques RLS pour sécuriser l’accès aux données. | `CREATE POLICY "Les utilisateurs peuvent voir leurs propres tâches" ON Tâche FOR SELECT...`. |
| **Commentaires** | Ajouter des commentaires pour documenter le schéma. | `-- Table pour stocker les tâches des utilisateurs`. |



# 6. Description des fonctionnalités intégrant l’intelligence artificielle


## 6.1. Introduction

Ce chapitre détaille comment **l’intelligence artificielle (IA)** est intégrée dans StudyFlow AI pour **automatiser**, **personnaliser** et **optimiser** l’expérience utilisateur. L’objectif est de répondre aux **besoins spécifiques** des étudiants et des professeurs en utilisant des **modèles d’IA avancés** (Mistral AI, Vibe Coding, etc.) tout en garantissant une **approche éthique**, **sécurisée** et **scalable**.

L’IA dans StudyFlow AI couvre :

- **L’analyse des besoins** (comprendre les objectifs et lacunes des utilisateurs).

- **La génération de contenu** (quiz, plans de révision, ressources adaptées).

- **L’automatisation des tâches** (planification intelligente, corrections, notifications).

- **L’assistance en temps réel** (chatbot, recommandations contextuelles).


## 6.2. Opportunités clés pour l’IA dans StudyFlow AI

L’IA offre **5 opportunités majeures** pour StudyFlow AI, classées par **valeur ajoutée** et **priorité d’implémentation** :

| **Opportunité** | **Description** | **Problème utilisateur résolu** | **Pattern d’intégration** | **Valeur mesurable** | **Difficulté d’implémentation** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| **Planification intelligente** | Optimisation dynamique des tâches et révisions en fonction des échéances, lacunes et habitudes. | Difficulté à prioriser les tâches, surcharge cognitive. | **Agents autonomes** (LangChain) + **Règles métiers** pour le tri des tâches. | Gain de temps (réduction de 30% du temps d’organisation), meilleure couverture des sujets. | ⭐⭐⭐⭐ (4) |
| **Chatbot IA** | Assistant conversationnel pour répondre aux questions, expliquer des concepts, guider les utilisateurs. | Manque d’explications adaptées, difficulté à comprendre les concepts complexes. | **Mistral AI** ou **Vibe Coding** pour des réponses contextuelles et personnalisées. | Réduction de 40% des questions répétitives, satisfaction utilisateur accrue. | ⭐⭐⭐⭐⭐ (5) |
| **Génération de quiz adaptatifs** | Création automatique de quiz en fonction des lacunes et du niveau de l’étudiant. | Manque de ressources adaptées, difficulté à évaluer ses progrès. | **Mistral AI** ou **GPT** pour générer des questions ciblées. | Amélioration de 25% des scores aux quiz, apprentissage plus efficace. | ⭐⭐⭐ (3) |
| **Analyse prédictive** | Analyse des performances pour prédire les difficultés et recommander des actions. | Difficulté à évaluer ses progrès, manque de feedback personnalisé. | **Analyse de données** (Python + Pandas) + **Modèles de prédiction** (Scikit-learn). | Réduction de 20% des échecs aux examens grâce à des recommandations proactives. | ⭐⭐⭐⭐ (4) |
| **Automatisation de la collaboration** | Modération des groupes, classification des ressources, suggestions de partenaires. | Manque de collaboration efficace, outils non intégrés. | **Agents autonomes** pour la modération + **NLP** pour la classification des ressources. | Augmentation de 30% de l’engagement dans les groupes collaboratifs. | ⭐⭐⭐⭐ (4) |



## 6.3. Comparaison des approches pour l’intégration de l’IA

Trois **approches principales** ont été évaluées pour l’intégration de l’IA dans StudyFlow AI. Voici une comparaison détaillée :

| **Critère** | **Approche 1 : Génération complète par LLM** | **Approche 2 : Règles métiers + LLM ponctuel** | **Approche 3 : Extraction + Présentation structurée** |
| :-: | :-: | :-: | :-: |
| **Description** | Utilisation exclusive d’un **Large Language Model (LLM)** pour générer toutes les réponses et actions. | Combinaison de **règles métiers** (pour les tâches simples) et de **LLM** (pour les cas complexes). | **Extraction** des données utilisateurs + **présentation structurée** (sans génération automatique). |
| **Flexibilité** | ⭐⭐⭐⭐⭐ (Très flexible, peut gérer des requêtes imprévues). | ⭐⭐⭐⭐ (Flexible pour les cas complexes, mais limité par les règles métiers). | ⭐⭐ (Peu flexible, dépend des données existantes). |
| **Coût** | ⭐ (Élevé : coût des API LLM pour chaque requête). | ⭐⭐⭐ (Modéré : coût réduit grâce aux règles métiers). | ⭐⭐⭐⭐⭐ (Faible : pas de coût LLM). |
| **Transparence** | ⭐ (Faible : décisions difficiles à expliquer). | ⭐⭐⭐⭐ (Bonne : règles métiers claires + LLM pour les cas complexes). | ⭐⭐⭐⭐⭐ (Excellente : toutes les décisions sont basées sur des données structurées). |
| **Complexité technique** | ⭐⭐⭐⭐ (Élevée : intégration complexe avec les LLM). | ⭐⭐⭐ (Modérée : nécessite une bonne conception des règles métiers). | ⭐ (Faible : simple à implémenter). |
| **Performance** | ⭐⭐ (Lente : latence due aux appels API LLM). | ⭐⭐⭐⭐ (Bonne : règles métiers rapides + LLM ponctuel). | ⭐⭐⭐⭐⭐ (Excellente : pas de latence). |
| **Adaptabilité** | ⭐⭐⭐⭐⭐ (Très adaptable à de nouveaux cas d’usage). | ⭐⭐⭐⭐ (Adaptable, mais nécessite des mises à jour des règles métiers). | ⭐ (Peu adaptable : nécessite des modifications manuelles des données). |
| **Recommandation pour le MVP** | ❌ Non recommandée (coût et latence trop élevés). | ✅ **Recommandée** (équilibre optimal entre flexibilité, coût et performance). | ⚠️ À considérer pour des fonctionnalités spécifiques (ex : tableau de bord). |



**Synthèse** :

- **Approche 1** : Idéale pour un produit **ultra-flexible**, mais **trop coûteuse** pour le MVP.

- **Approche 2** : **Équilibre optimal** pour le MVP : **règles métiers + LLM ponctuel**.

- **Approche 3** : **Simple et économique**, mais **peu automatisée**.


## 6.4. Approche hybride recommandée pour le MVP

Pour le **MVP de StudyFlow AI**, l’**approche hybride (Approche 2)** est recommandée. Elle combine :

- **Des règles métiers** pour les tâches simples et répétitives (ex : tri des tâches par échéance).

- **Un LLM (Mistral AI)** pour les cas complexes (ex : génération de quiz, planification intelligente).

### **6.4.1. Workflow utilisateur avec l’approche hybride**

![Hybride](Graph-Hybride.png)


### **6.4.2. Exemples concrets d’intégration**

| **Fonctionnalité** | **Règles métiers** | **LLM (Mistral AI)** | **Bénéfice** |
| :-: | :-: | :-: | :-: |
| **Planification intelligente** | Tri des tâches par échéance et priorité. | Optimisation du planning en fonction des **lacunes** et des **habitudes** de l’utilisateur. | Planning **personnalisé** et **efficace**. |
| **Génération de quiz** | Sélection des questions parmi une base prédéfinie. | Génération de **questions adaptées** aux lacunes de l’utilisateur. | Quiz **ciblés** et **pertinents**. |
| **Chatbot IA** | Réponses aux questions fréquentes (ex : |  |  |


