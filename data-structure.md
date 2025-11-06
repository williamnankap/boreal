# 🐍 Cours Python - Les Structures de Données

> Cours complet sur les Listes, Tuples, Dictionnaires et Sets en Python

---

## 📋 Table des Matières

1. [Introduction](#introduction)
2. [Prérequis](#prérequis)
3. [Les Structures de Données](#les-structures-de-données)
   - [Listes (Lists)](#1️⃣-listes-lists)
   - [Tuples](#2️⃣-tuples)
   - [Dictionnaires (Dictionaries)](#3️⃣-dictionnaires-dictionaries)
   - [Ensembles (Sets)](#4️⃣-ensembles-sets)
4. [Comparaison](#comparaison-des-structures)
5. [Exercices](#exercices-pratiques)
6. [Ressources](#ressources-supplémentaires)

---

## Introduction

Ce cours couvre les quatre principales structures de données en Python. Vous apprendrez à :
- ✅ Créer et manipuler des listes, tuples, dictionnaires et sets
- ✅ Choisir la structure appropriée selon vos besoins
- ✅ Maîtriser les opérations courantes sur chaque structure
- ✅ Résoudre des problèmes pratiques

---

## Prérequis

- Python 3.x installé
- Connaissances de base en Python (variables, boucles, conditions)
- Un éditeur de code (VS Code, PyCharm, etc.)

---

## Les Structures de Données

### 1️⃣ Listes (Lists)

**Collection ordonnée et modifiable**

#### Syntaxe
```python
ma_liste = [1, 2, 3, 4, 5]
fruits = ["pomme", "banane", "orange"]
mixte = [1, "Python", 3.14, True]
```

#### Opérations principales
```python
# Accès
print(fruits[0])           # Premier élément
print(fruits[-1])          # Dernier élément
print(fruits[1:3])         # Slicing

# Modification
fruits.append("kiwi")      # Ajouter à la fin
fruits.insert(1, "mangue") # Insérer à l'index
fruits.remove("pomme")     # Supprimer
fruits.pop()               # Retirer le dernier

# Méthodes utiles
fruits.sort()              # Trier
fruits.reverse()           # Inverser
len(fruits)                # Longueur
fruits.count("banane")     # Compter occurrences
```

#### Parcourir une liste
```python
# Méthode 1
for fruit in fruits:
    print(fruit)

# Méthode 2 avec index
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")
```

---

### 2️⃣ Tuples

**Collection ordonnée et immuable**

#### Syntaxe
```python
mon_tuple = (1, 2, 3)
coordonnees = (10.5, 20.3)
un_element = (5,)  # ⚠️ Virgule obligatoire !
```

#### Caractéristiques
```python
# Accès (comme les listes)
print(coordonnees[0])

# ❌ IMPOSSIBLE de modifier
# coordonnees[0] = 15  # TypeError!

# Déballage (unpacking)
x, y = coordonnees
a, b = b, a  # Échange de variables
```

#### Pourquoi utiliser des tuples ?
- ✅ Plus rapides et moins gourmands en mémoire
- ✅ Protègent vos données (immuabilité)
- ✅ Peuvent servir de clés de dictionnaire
- ✅ Idéaux pour des données fixes (coordonnées, dates, etc.)

---

### 3️⃣ Dictionnaires (Dictionaries)

**Collection de paires clé-valeur**

#### Syntaxe
```python
etudiant = {
    "nom": "Dupont",
    "prenom": "Jean",
    "age": 20,
    "notes": [15, 18, 16]
}

# Autre syntaxe
personne = dict(nom="Martin", age=25)
```

#### Opérations principales
```python
# Accès
print(etudiant["nom"])              # Peut générer KeyError
print(etudiant.get("age", 0))       # Sécurisé avec valeur par défaut

# Modification
etudiant["age"] = 21                # Modifier
etudiant["ville"] = "Paris"         # Ajouter
del etudiant["ville"]               # Supprimer
age = etudiant.pop("age")           # Retirer et retourner

# Méthodes utiles
etudiant.keys()                     # Toutes les clés
etudiant.values()                   # Toutes les valeurs
etudiant.items()                    # Paires (clé, valeur)
"nom" in etudiant                   # Vérifier existence
```

#### Parcourir un dictionnaire
```python
# Parcourir clés et valeurs
for cle, valeur in etudiant.items():
    print(f"{cle}: {valeur}")

# Parcourir uniquement les clés
for cle in etudiant:
    print(cle)

# Parcourir uniquement les valeurs
for valeur in etudiant.values():
    print(valeur)
```

---

### 4️⃣ Ensembles (Sets)

**Collection d'éléments uniques non ordonnée**

#### Syntaxe
```python
nombres = {1, 2, 3, 4, 5}
fruits = {"pomme", "banane", "orange"}

# ⚠️ Set vide
mon_set = set()  # ✅ Correct
# mon_set = {}   # ❌ Ceci crée un dictionnaire!
```

#### Opérations principales
```python
# Ajouter
fruits.add("kiwi")
fruits.update(["mangue", "pêche"])

# Supprimer
fruits.remove("pomme")      # Erreur si inexistant
fruits.discard("poire")     # Pas d'erreur
element = fruits.pop()      # Retire aléatoirement

# Éliminer les doublons
liste = [1, 2, 2, 3, 3, 3, 4]
uniques = set(liste)  # {1, 2, 3, 4}
```

#### Opérations ensemblistes
```python
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}

A | B        # Union: {1, 2, 3, 4, 5, 6, 7, 8}
A & B        # Intersection: {4, 5}
A - B        # Différence: {1, 2, 3}
A ^ B        # Différence symétrique: {1, 2, 3, 6, 7, 8}

A.issubset(B)       # A est sous-ensemble de B ?
A.issuperset(B)     # A est sur-ensemble de B ?
```

---

## Comparaison des Structures

| Caractéristique | Liste | Tuple | Dictionnaire | Set |
|----------------|-------|-------|--------------|-----|
| **Syntaxe** | `[]` | `()` | `{k:v}` | `{v}` |
| **Ordonnée** | ✅ | ✅ | ✅ (3.7+) | ❌ |
| **Modifiable** | ✅ | ❌ | ✅ | ✅ |
| **Doublons** | ✅ | ✅ | Clés ❌ | ❌ |
| **Indexation** | Par index | Par index | Par clé | ❌ |
| **Performance** | Moyenne | Rapide | Très rapide | Rapide |
| **Usage mémoire** | Moyen | Faible | Élevé | Moyen |

### 🎯 Quand utiliser quoi ?

**Listes** 📋
- Données ordonnées et modifiables
- Accès par index nécessaire
- Collections de taille variable

**Tuples** 🔒
- Données immuables et sûres
- Coordonnées, dates, configurations
- Clés de dictionnaire
- Performance critique

**Dictionnaires** 📖
- Association clé-valeur
- Recherche rapide par clé
- Données structurées (JSON-like)
- Configurations, paramètres

**Sets** 🎯
- Éliminer les doublons
- Opérations mathématiques (union, intersection)
- Test d'appartenance rapide
- L'ordre n'importe pas

---

## Exercices Pratiques

### 🔰 Niveau Débutant

#### Exercice 1 : Liste de courses
```python
# Créez une liste de courses avec 5 articles
# Ajoutez 2 articles
# Supprimez le premier article
# Affichez le nombre d'articles
```

#### Exercice 2 : Coordonnées GPS
```python
# Créez un tuple pour Paris (48.8566, 2.3522)
# Déballez les coordonnées dans latitude et longitude
# Essayez de modifier une coordonnée (observez l'erreur)
```

#### Exercice 3 : Carnet d'adresses
```python
# Créez un dictionnaire avec 3 contacts (nom, téléphone, email)
# Affichez toutes les clés
# Ajoutez un nouveau contact
# Modifiez le téléphone d'un contact
```

#### Exercice 4 : Nombres uniques
```python
# Créez une liste avec des doublons: [1, 2, 2, 3, 3, 3, 4, 5, 5]
# Convertissez-la en set pour éliminer les doublons
# Affichez le nombre d'éléments uniques
```

---

### 🔥 Niveau Intermédiaire

#### Exercice 5 : Statistiques de notes
```python
notes = [15, 18, 12, 15, 19, 14, 15, 16, 12]

# Calculez:
# - La moyenne
# - La note max et min
# - Le nombre de notes >= 15
# - Créez un dictionnaire {note: nombre_occurrences}
```

<details>
<summary>💡 Solution</summary>

```python
moyenne = sum(notes) / len(notes)
note_max = max(notes)
note_min = min(notes)
bonnes_notes = len([n for n in notes if n >= 15])

occurrences = {}
for note in notes:
    occurrences[note] = occurrences.get(note, 0) + 1
```
</details>

---

#### Exercice 6 : Analyse de texte
```python
texte = "python est un langage de programmation python est génial"

# 1. Séparez en mots (liste)
# 2. Trouvez les mots uniques (set)
# 3. Comptez les occurrences de chaque mot (dictionnaire)
# 4. Trouvez le mot le plus fréquent
```

<details>
<summary>💡 Solution</summary>

```python
mots = texte.split()
mots_uniques = set(mots)

occurrences = {}
for mot in mots:
    occurrences[mot] = occurrences.get(mot, 0) + 1

mot_frequent = max(occurrences, key=occurrences.get)
print(f"Mot le plus fréquent: {mot_frequent} ({occurrences[mot_frequent]} fois)")
```
</details>

---

#### Exercice 7 : Comparaison de cours
```python
cours_alice = {"Python", "Java", "SQL", "HTML"}
cours_bob = {"Python", "JavaScript", "HTML", "CSS"}

# Trouvez:
# - Les cours en commun
# - Les cours suivis uniquement par Alice
# - Les cours suivis uniquement par Bob
# - Tous les cours différents suivis
```

<details>
<summary>💡 Solution</summary>

```python
communs = cours_alice & cours_bob
seulement_alice = cours_alice - cours_bob
seulement_bob = cours_bob - cours_alice
tous_cours = cours_alice | cours_bob
```
</details>

---

### 🚀 Niveau Avancé

#### Exercice 8 : Gestion de bibliothèque
```python
# Créez un système de gestion avec:
# - Dictionnaire de livres (titre, auteur, année, disponible)
# - Fonction pour emprunter un livre
# - Fonction pour retourner un livre
# - Fonction pour lister les livres disponibles
# - Fonction pour chercher par auteur
```

---

#### Exercice 9 : Inventaire de magasin
```python
# Créez un inventaire avec:
# - Dictionnaire {produit: (prix, quantité)}
# - Fonction pour ajouter du stock
# - Fonction pour vendre (diminuer stock)
# - Fonction pour calculer la valeur totale de l'inventaire
# - Alertes pour produits en rupture de stock
```

---

#### Exercice 10 : Analyse de données
```python
# Données de ventes mensuelles
ventes = [
    {"mois": "Jan", "produit": "A", "montant": 1500},
    {"mois": "Jan", "produit": "B", "montant": 2000},
    {"mois": "Fev", "produit": "A", "montant": 1800},
    # ... etc
]

# Calculez:
# - Total des ventes par mois
# - Total des ventes par produit
# - Mois avec le plus de ventes
# - Produit le plus vendu
```

---

## 📊 Tableau de Complexité

| Opération | Liste | Tuple | Dict | Set |
|-----------|-------|-------|------|-----|
| Accès par index | O(1) | O(1) | - | - |
| Recherche | O(n) | O(n) | O(1) | O(1) |
| Insertion | O(n) | - | O(1) | O(1) |
| Suppression | O(n) | - | O(1) | O(1) |
| Parcours | O(n) | O(n) | O(n) | O(n) |

---

## 💡 Astuces et Bonnes Pratiques

### Listes
```python
# List comprehension (élégant et rapide)
carres = [x**2 for x in range(10)]

# Copie de liste
liste2 = liste1.copy()  # ✅ Correct
liste2 = liste1[:]      # ✅ Aussi correct
liste2 = liste1         # ❌ Référence, pas copie!
```

### Dictionnaires
```python
# Valeur par défaut avec setdefault
compteur.setdefault(mot, 0)
compteur[mot] += 1

# Fusion de dictionnaires (Python 3.9+)
dict3 = dict1 | dict2
```

### Sets
```python
# Tester l'appartenance (très rapide)
if element in mon_set:  # O(1) vs O(n) pour liste
    pass

# Convertir en liste triée
liste_triee = sorted(mon_set)
```

---

## 🔍 Pièges Courants à Éviter

### 1. Modification pendant l'itération
```python
# ❌ Mauvais
for item in ma_liste:
    if condition:
        ma_liste.remove(item)

# ✅ Bon
ma_liste = [item for item in ma_liste if not condition]
```

### 2. Copie superficielle vs profonde
```python
import copy

# Copie superficielle
liste2 = liste1.copy()

# Copie profonde (pour listes imbriquées)
liste2 = copy.deepcopy(liste1)
```

### 3. Dictionnaire avec valeurs mutables
```python
# ❌ Problème potentiel
mon_dict = {}
for key in keys:
    mon_dict[key] = []  # Nouvelle liste à chaque fois ✅

# vs

default_list = []
for key in keys:
    mon_dict[key] = default_list  # ❌ Même référence!
```

---

## 🎓 Quiz Rapide

1. Quelle structure choisir pour stocker des coordonnées GPS ?
2. Comment éliminer les doublons d'une liste ?
3. Peut-on utiliser une liste comme clé de dictionnaire ?
4. Quelle est la différence entre `remove()` et `discard()` pour un set ?
5. Comment créer un dictionnaire avec des valeurs par défaut ?

<details>
<summary>Réponses</summary>

1. Tuple (immuable et efficace)
2. `set(ma_liste)` ou `list(set(ma_liste))`
3. Non, seulement des types immuables (tuple oui)
4. `remove()` génère une erreur si absent, `discard()` non
5. Utiliser `collections.defaultdict` ou `dict.setdefault()`
</details>

---

## Ressources Supplémentaires

### Documentation Officielle
- [Python Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)
- [Python Tuples](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences)
- [Python Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)
- [Python Sets](https://docs.python.org/3/tutorial/datastructures.html#sets)

### Modules Avancés
- `collections` : Structures de données spécialisées
  - `defaultdict`, `Counter`, `OrderedDict`, `deque`
- `array` : Tableaux typés efficaces
- `heapq` : Files de priorité

### Tutoriels Recommandés
- Real Python - Python Data Structures
- W3Schools - Python Collections
- GeeksforGeeks - Python Data Structures

---

## 🤝 Contribution

Ce cours est en constante évolution. N'hésitez pas à :
- Signaler des erreurs
- Proposer des améliorations
- Ajouter des exercices
- Partager vos solutions



*Dernière mise à jour : Novembre 2025*
