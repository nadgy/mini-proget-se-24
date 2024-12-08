# Mini-Projet Système d'éxploitation

***Choisissez un thème unique***

**Mini-Projet 1: Gestion de Threads - Producteur/Consommateur**

### Contexte :
Dans les systèmes multitâches, la communication et la synchronisation entre différentes entités jouent un rôle crucial. Ce projet consiste à implémenter un système où un ou plusieurs **Producteurs** génèrent des données et les insèrent dans un tampon circulaire, tandis qu'un ou plusieurs **Consommateurs** récupèrent et traitent ces données. L'objectif principal est de comprendre les mécanismes de synchronisation des threads et de maîtriser le fonctionnement d'un tampon circulaire.

### Objectifs :
1. Comprendre le fonctionnement des threads et les mécanismes de synchronisation (mutex, sémaphores).
2. Implémenter une solution robuste au problème classique **Producteur-Consommateur**.
3. Apprendre et appliquer les techniques de gestion d'un **tampon circulaire**.

### Description du Problème :
- **Producteur** : Un ou plusieurs threads qui génèrent des données et les écrivent dans un tampon circulaire.
- **Consommateur** : Un ou plusieurs threads qui lisent les données du tampon pour les traiter.

Le tampon circulaire a une taille fixe. Le système doit garantir :
- Le producteur ne doit pas écrire dans le tampon si celui-ci est plein.
- Le consommateur ne doit pas lire dans le tampon si celui-ci est vide.
- Une gestion coordonnée entre les threads pour éviter les conditions de course et assurer l'intégrité des données.

### Contraintes :
- Utiliser **uniquement des threads** (pas de mémoire partagée ou processus).
- Implémenter le projet en **C**.
- Le tampon doit fonctionner de manière circulaire (lorsqu'il est plein, le producteur attend qu'un consommateur libère de l'espace).

### Tâches à réaliser :
1. **Création des threads et du tampon circulaire** :
   - Créer un tampon circulaire bien structuré avec des métadonnées nécessaires (indices de lecture/écriture, taille actuelle, etc.).
   - Créer des threads pour les producteurs et les consommateurs.

2. **Synchronisation des threads** :
   - Mettre en place les primitives de synchronisation comme les mutex et sémaphores pour assurer un accès coordonné au tampon.

3. **Implémentation des threads** :
   - Implémenter les threads producteurs qui génèrent des données et les insèrent dans le tampon.
   - Implémenter les threads consommateurs qui récupèrent et traitent les données du tampon.

4. **Tests et validations** :
   - Simuler plusieurs producteurs et consommateurs.
   - Vérifier le bon fonctionnement du tampon circulaire et l'absence de conditions de course.

### Extensions Possibles :
- Ajouter des statistiques sur l'utilisation du tampon (taux de remplissage moyen, temps d'attente des producteurs/consommateurs).
- Gérer des priorités différentes entre les producteurs et les consommateurs.
- Implémenter une visualisation en console pour suivre l'état du tampon en temps réel.

### Livrables :
1. Code source documenté.(commenté) 
2. Rapport expliquant :(facultatif)
   - La conception adoptée.
   - Les problèmes rencontrés et leurs solutions.
   - Une analyse des performances du système.

3. Une démonstration montrant le fonctionnement du système .

### Barème d’évaluation :
1. Fonctionnalité de base (50%) : Le système fonctionne correctement avec au moins un producteur et un consommateur.
2. Gestion de la synchronisation (30%) : Les mécanismes garantissent l'absence de conditions de course et un fonctionnement fluide.
3. Extensions et innovations (20%) : Toute amélioration ou ajout fonctionnel apporté au projet de base.


---

**Mini-Projet 2: Gestion de la Mémoire Partagée - Lecteurs/Rédacteurs**

### Contexte :
La gestion des ressources partagées dans les systèmes d'exploitation est essentielle pour garantir l'accès concurrent à des données communes sans provoquer de conflits ou d'incohérences. Ce projet se concentre sur l'implémentation du problème classique des **Lecteurs/Rédacteurs**, où plusieurs processus doivent accéder à une mémoire partagée tout en respectant des règles de synchronisation précises.

### Objectifs :
1. Comprendre les principes de la synchronisation entre processus.
2. Utiliser la mémoire partagée pour implémenter une solution au problème des **Lecteurs/Rédacteurs**.
3. Appliquer des mécanismes de contrôle d'accès comme les mutex, sémaphores, ou autres primitives de synchronisation.

### Description du Problème :
- **Lecteurs** : Plusieurs processus qui accèdent à la mémoire partagée pour lire des données. Les lecteurs peuvent accéder simultanément à la mémoire s'il n'y a aucun rédacteur actif.
- **Rédacteurs** : Plusieurs processus qui modifient les données dans la mémoire partagée. Les rédacteurs doivent avoir un accès exclusif.

Le système doit garantir :
- Plusieurs lecteurs peuvent lire en même temps si aucun rédacteur n’écrit.
- Un seul rédacteur peut accéder à la mémoire à la fois.
- Si un rédacteur souhaite accéder à la mémoire, aucun nouveau lecteur ne doit commencer une lecture tant que l’écriture n’est pas terminée.

### Contraintes :
- Utiliser des **processus** (pas de threads).
- Utiliser la **mémoire partagée** pour les données partagées entre lecteurs et rédacteurs.
- Implémenter le projet en **C**.
- Garantir la synchronisation des accès à l’aide de primitives comme les sémaphores ou les mutex.

### Tâches à réaliser :
1. **Initialisation de la mémoire partagée** :
   - Créer une région de mémoire partagée pour stocker les données communes et les métadonnées (par exemple, compteurs de lecteurs, état de l'accès).

2. **Implémentation des processus** :
   - Créer des processus lecteurs qui accèdent simultanément à la mémoire partagée pour lire les données.
   - Créer des processus rédacteurs qui modifient les données tout en assurant un accès exclusif.

3. **Synchronisation des processus** :
   - Utiliser des sémaphores pour contrôler l’accès concurrent des lecteurs et rédacteurs.
   - Garantir qu’aucun lecteur ne commence une lecture pendant qu’un rédacteur est actif, et vice versa.

4. **Tests et validations** :
   - Simuler plusieurs processus lecteurs et rédacteurs.
   - S’assurer que le système respecte les règles de synchronisation et qu’aucune condition de course n’apparaît.

### Extensions Possibles :
- Implémenter une stratégie pour éviter la famine (priorité aux lecteurs ou aux rédacteurs).
- Ajouter des statistiques sur les temps d’attente des lecteurs et des rédacteurs.
- Visualiser l’état de la mémoire partagée en temps réel (console ou interface graphique).

### Livrables :
1. Code source documenté.(commenté) 
2. Rapport expliquant :(facultatif)
   - La conception adoptée.
   - Les problèmes rencontrés et leurs solutions.
   - Une analyse des performances et des limitations.

3. Une démonstration montrant le fonctionnement du système.

### Barème d’évaluation :
1. Fonctionnalité de base (50%) : Le système respecte les règles de synchronisation avec au moins un lecteur et un rédacteur.
2. Gestion de la synchronisation (30%) : Les mécanismes employés garantissent l’intégrité et la sécurité des données.
3. Extensions et innovations (20%) : Toute fonctionnalité supplémentaire ou optimisation apportée au projet de base.


