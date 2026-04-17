# 🚚 Projet Mobilité Multimodale Intelligente - CESI x ADEME

## 📌 Présentation du Projet
L'objectif est d'optimiser les tournées de livraison pour réduire l'empreinte carbone, en résolvant un problème de voyageur de commerce (TSP) enrichi de contraintes réelles :
1. **Fenêtres Temporelles (Time Windows)** : Respect des horaires de livraison.
2. **Restrictions d'Arêtes** : Prise en compte des routes bloquées ou coûteuses (bouchons).

---

## ✅ Ce qui a été réalisé

### 1. Modélisation Théorique
- Formalisation mathématique du problème.
- Définition de la fonction objectif (minimisation du temps total + pénalités).
- Analyse de la complexité (Problème NP-Difficile).

### 2. Générateur d'Instances (Python Natif)
- Génération de coordonnées aléatoires.
- Création d'une **"Tournée Fantôme"** pour garantir la faisabilité.
- Application de contraintes dynamiques sur les arêtes (coûts et blocages).
- Génération de fenêtres de temps cohérentes autour de la solution garantie.

### 3. Méthode de Résolution 1 : Métaheuristique
- Implémentation du **Recuit Simulé (Simulated Annealing)**.
- Système d'évaluation avec **pénalités de retard et d'interdiction**.
- Validation : L'algorithme retrouve avec succès la solution optimale sur des instances de test (Coût 233).

---

## 🚀 Ce qu'il reste à faire (Roadmap)

### Étape A : Méthode de Résolution Exacte (PuLP)
- Traduire le modèle mathématique en Programmation Linéaire.
- Utiliser un solveur (CBC/Gurobi) pour obtenir la solution prouvée optimale.
- Comparer les résultats avec le Recuit Simulé.

### Étape B : Visualisation Dynamique
- Créer un rendu graphique avec `Matplotlib`.
- Animation de l'évolution de la tournée au fil des itérations du Recuit Simulé.
- Affichage des fenêtres de temps (code couleur : ouvert/fermé).

### Étape C : Étude Expérimentale & Statistique
- Benchmarks de performance : Temps d'exécution vs Taille de l'instance.
- Analyse de la qualité des solutions : Écart à l'optimalité (Gap) de la métaheuristique.
- Rédaction du rapport final pour l'ADEME.