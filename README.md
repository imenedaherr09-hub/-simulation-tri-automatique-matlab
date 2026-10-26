# CAHIER DES CHARGES

## Modélisation et simulation sous MATLAB d'un système automatisé de tri d'objets

**Projet universitaire — 4e année**

| | |
|---|---|
| **Nom** | Daher |
| **Prénom** | Imene |
| **Matricule** | 222231694713 |
| **Département** | Automatique |
| **Spécialité** | Robotique et Systèmes Intelligents |
| **Établissement** | USTHB |
| **Environnement de développement** | MATLAB R2018a |
| **Type de réalisation** | Simulation numérique, sans matériel physique |
| **Durée prévisionnelle** | 8 semaines |

*Document de cadrage initial — les seuils de taille et les règles exactes d'affectation aux bacs seront fixés et validés pendant le développement.*

---

## 1. Introduction

### 1.1 Contexte

Le tri automatique est une fonction courante dans les systèmes de production et de manutention. Il permet d'identifier des objets à partir de caractéristiques définies, puis de les orienter vers des destinations différentes. Ce projet vise à étudier ce principe à travers une simulation graphique réalisée sous MATLAB, sans construction d'un dispositif réel.

### 1.2 Problématique

Comment représenter et simuler un système capable de faire avancer des objets sur un tapis roulant, d'évaluer leur taille et leur forme dans une zone de détection virtuelle, puis de les diriger vers le bac correspondant selon des règles de tri prédéfinies ?

### 1.3 Objectif général

Développer sous MATLAB R2018a une simulation fonctionnelle d'un système automatisé de tri d'objets selon leur taille et leur forme.

### 1.4 Objectifs spécifiques

- Représenter graphiquement un tapis roulant, une zone de détection, une zone de tri et trois bacs de réception.
- Créer des objets virtuels de formes géométriques différentes et de tailles différentes.
- Simuler le déplacement des objets le long du tapis.
- Déterminer, par traitement numérique, la catégorie de taille et la forme de chaque objet.
- Appliquer des règles de décision pour affecter les objets aux bacs.
- Afficher les résultats de la simulation et vérifier le fonctionnement à l'aide de scénarios de test.

### 1.5 Besoins identifiés

- Une représentation visuelle claire du fonctionnement du système.
- Une classification reproductible fondée sur les caractéristiques virtuelles des objets.
- Un programme structuré, lisible et modifiable.
- La possibilité de tester plusieurs objets et de vérifier leur destination.

---

## 2. Spécifications techniques

### 2.1 Fonctions attendues

- **F1 — Génération des objets** : créer des objets virtuels avec une forme et une taille connues.
- **F2 — Déplacement** : faire progresser les objets sur un tapis roulant simulé.
- **F3 — Détection virtuelle** : repérer le passage d'un objet dans une zone de détection et lire ses paramètres simulés.
- **F4 — Classification** : déterminer la forme et la catégorie de taille à partir des paramètres numériques de l'objet.
- **F5 — Décision** : appliquer des règles de tri définies dans le programme.
- **F6 — Orientation** : simuler l'envoi de l'objet vers l'un des trois bacs.
- **F7 — Affichage** : visualiser le déplacement, la catégorie reconnue et la destination.

### 2.2 Entrées et sorties

| Éléments | Description |
|---|---|
| Entrées | Forme de l'objet, dimensions ou paramètre de taille, position initiale et vitesse de déplacement simulée. |
| Traitement | Déplacement numérique, détection dans une zone virtuelle, classification et application des règles de décision. |
| Sorties | Animation ou mise à jour graphique, catégorie attribuée, bac de destination et bilan du tri. |

### 2.3 Paramètres et limites prévues

- La scène comprend un tapis roulant, une zone de détection virtuelle, une zone de tri et trois bacs.
- Les formes seront représentées par des géométries simples, par exemple cercle, carré et triangle.
- Les tailles seront définies par des dimensions numériques et regroupées en catégories selon des seuils fixés pendant le développement.
- Le système traite les objets à partir de leurs paramètres simulés : aucune caméra ni aucun capteur physique ne sont utilisés.
- Les règles exactes reliant les formes et tailles aux trois bacs seront documentées dans le programme et vérifiées par des essais.

### 2.4 Contraintes techniques

- Le logiciel de référence est MATLAB R2018a.
- Le projet doit rester réalisable sans matériel physique et sans acquisition de données réelle.
- Le programme doit être organisé en scripts et, si nécessaire, en fonctions séparées.
- L'animation doit rester suffisamment fluide pour observer le déplacement des objets sur l'ordinateur utilisé.

---

## 3. Environnement de travail

### 3.1 Environnement logiciel

Le développement sera réalisé sous MATLAB R2018a. Les fonctions graphiques de base de MATLAB seront utilisées pour dessiner la scène, représenter les objets et actualiser leurs positions. Les opérations de classification seront effectuées à partir des valeurs numériques définies dans le programme.

### 3.2 Environnement simulé

Le système sera représenté dans une scène bidimensionnelle. Les objets avanceront sur un tapis roulant virtuel, passeront devant une zone de détection, puis seront dirigés vers un bac de réception. La simulation ne représente pas nécessairement toutes les dimensions et contraintes d'une installation industrielle réelle.

### 3.3 Contraintes et hypothèses

- Les objets sont supposés suffisamment espacés pour pouvoir être traités individuellement dans la première version.
- Les caractéristiques de chaque objet sont connues dans le modèle numérique ; il ne s'agit pas d'une reconnaissance par caméra.
- Les effets physiques détaillés, tels que les frottements, les collisions complexes ou les défauts mécaniques, ne sont pas modélisés dans le périmètre initial.
- Les valeurs de vitesse, de taille et les positions des zones pourront être ajustées au cours des essais.

---

## 4. Intégration du système

### 4.1 Architecture fonctionnelle

La simulation sera organisée autour des étapes suivantes : génération des objets → déplacement sur le tapis → passage dans la zone de détection virtuelle → classification par forme et taille → décision de tri → orientation vers un bac → affichage des résultats.

### 4.2 Organisation logicielle

- Un script principal initialise la scène, les paramètres et le déroulement de la simulation.
- Des instructions ou fonctions dédiées gèrent la création des objets et la mise à jour de leur position.
- Un bloc de traitement détermine la forme et la catégorie de taille de chaque objet.
- Un bloc de décision choisit le bac de destination selon les règles établies.
- Une partie d'affichage montre les objets et peut présenter un bilan du nombre d'objets triés.

### 4.3 Interfaces et limites d'intégration

Le système fonctionne de manière autonome dans MATLAB. Aucune connexion à un automate programmable, à un convoyeur réel, à une caméra ou à des capteurs physiques n'est prévue. Le code et les résultats pourront être conservés dans un dépôt GitHub afin de suivre l'évolution du projet et de partager les fichiers avec l'encadrant.

---

## 5. Critères d'acceptation

Le projet sera considéré comme acceptable si les tests suivants sont satisfaits :

| Test | Critère attendu |
|---|---|
| T1 — Affichage | La scène montre correctement le tapis, les zones de détection et de tri, ainsi que les trois bacs. |
| T2 — Déplacement | Les objets avancent sur le tapis sans disparition prématurée ni blocage inattendu dans le scénario normal. |
| T3 — Classification | Pour chaque objet de test, la forme et la catégorie de taille calculées correspondent aux paramètres définis au départ. |
| T4 — Décision de tri | Chaque objet est associé au bac prévu par les règles de décision documentées. |
| T5 — Tests variés | La simulation fonctionne avec plusieurs objets présentant différentes formes et tailles. |
| T6 — Résultats | Le résultat final permet de vérifier les destinations attribuées et, si possible, le nombre d'objets dans chaque bac. |

*Les tests seront effectués sur des objets dont les paramètres sont connus. La précision évaluée concerne donc la logique de classification programmée, et non la performance de capteurs réels.*

---

## 6. Planification et budget

### 6.1 Planification prévisionnelle

| Période | Travail prévu | Livrable |
|---|---|---|
| Semaine 1 | Analyse du besoin et définition des objets, formes, tailles et règles de tri. | Spécifications de départ. |
| Semaine 2 | Construction et amélioration de la scène graphique. | Scène MATLAB. |
| Semaine 3 | Création des objets et simulation de leur déplacement. | Déplacement fonctionnel. |
| Semaines 4–5 | Classification selon la forme et la taille, puis mise en place des règles de décision. | Logique de tri. |
| Semaine 6 | Tests de différents scénarios et correction des erreurs. | Résultats des tests. |
| Semaines 7–8 | Finalisation du programme, documentation, captures et préparation de la présentation. | Version finale et rapport. |

### 6.2 Budget prévisionnel

Le projet étant entièrement simulé, aucun achat de capteur, de moteur, de convoyeur ou de matériel de fabrication n'est prévu. Le budget matériel additionnel est donc estimé à 0 DA, sous réserve que l'ordinateur et l'accès à MATLAB soient déjà disponibles.

- Ordinateur : équipement existant, sans achat prévu.
- Logiciel MATLAB R2018a : accès existant ou fourni par l'établissement ; tout coût éventuel de licence dépend des conditions d'accès.
- Matériel physique : aucun.
- Documentation et partage des fichiers : dépôt GitHub, sans coût nécessaire pour les fonctions de base.

*Le budget ne comprend pas le temps de travail de l'étudiant. Cette estimation devra être adaptée si l'accès à MATLAB ou à l'équipement informatique entraîne un coût.*

---

## 7. Annexes

### Annexe A — Schéma fonctionnel textuel

1. Création d'un objet virtuel
2. ↓ Déplacement sur le tapis roulant
3. ↓ Passage dans la zone de détection virtuelle
4. ↓ Identification de la forme et de la taille
5. ↓ Application des règles de décision
6. ↓ Orientation vers le bac 1, 2 ou 3
7. ↓ Mise à jour du bilan de tri

### Annexe B — Éléments à documenter pendant le développement

- Les formes géométriques effectivement retenues.
- Les seuils numériques séparant les catégories de taille.
- La règle précise associant les combinaisons forme/taille aux trois bacs.
- Les paramètres de vitesse, de position et d'espacement des objets.
- Les résultats des tests et les éventuelles limites constatées.

### Annexe C — Références de réalisation

Le programme sera développé avec les fonctions graphiques et les opérations numériques disponibles dans MATLAB R2018a. Les noms des scripts, les fonctions utilisées et les captures de la simulation seront ajoutés au fur et à mesure de l'avancement du projet.

---

*Fin du cahier des charges — version initiale à valider avec l'encadrant.*



