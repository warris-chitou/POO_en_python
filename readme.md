# Programmation Orientée Objet (POO) en Python

La POO est un paradigme de programmation qui repose sur les **objets**, lesquels sont des représentations abstraites de concepts ou d’entités réelles. Elle permet d’organiser le code en regroupant **données** et **comportements**.

## 1. Concepts de base

### 1.1 Classe
Une classe est un modèle ou une structure définissant les caractéristiques (attributs) et les comportements (méthodes) des objets.  
**Exemple :**
```python
class Personne:
    def __init__(self, nom, age):  # Constructeur
        self.nom = nom
        self.age = age

    def se_presenter(self):  # Méthode
        return f"Je m'appelle {self.nom} et j'ai {self.age} ans."
```

### 1.2 Objet
Un objet est une **instance** de classe. C’est une entité concrète créée à partir d’une classe.  
**Exemple :**
```python
personne1 = Personne("Alice", 25)  # Création d'un objet
print(personne1.se_presenter())  # Appel d'une méthode
```

## 2. Principes fondamentaux de la POO

### 2.1 Encapsulation
**Définition** :  
- L’encapsulation consiste à regrouper les **données** (attributs) et les **méthodes** (comportements) dans une classe.  
- Elle protège les données en limitant leur accès direct depuis l’extérieur de la classe.  

**Exemple :**
```python
class CompteBancaire:
    def __init__(self, solde):
        self.__solde = solde  # Attribut privé (préfixé par __)

    def deposer(self, montant):
        self.__solde += montant

    def afficher_solde(self):
        return f"Solde : {self.__solde} €"

compte = CompteBancaire(100)
compte.deposer(50)
print(compte.afficher_solde())  # Accès indirect au solde
```

### 2.2 Héritage
**Définition** :  
L’héritage permet à une classe (sous-classe) de réutiliser les attributs et méthodes d’une autre classe (classe parent). Cela favorise la **réutilisation** et l’**extensibilité** du code.  

**Exemple :**
```python
class Animal:
    def parler(self):
        return "L'animal fait un bruit."

class Chien(Animal):  # Hérite de la classe Animal
    def parler(self):
        return "Le chien aboie."

mon_chien = Chien()
print(mon_chien.parler())  # Méthode redéfinie dans la sous-classe
```

### 2.3 Polymorphisme
**Définition** :  
Le polymorphisme permet d’utiliser une **même méthode** ou un **même comportement** sur différents objets, avec des résultats adaptés à chaque type d’objet.  

**Exemple :**
```python
class Chat(Animal):
    def parler(self):
        return "Le chat miaule."

animaux = [Chien(), Chat(), Animal()]
for animal in animaux:
    print(animal.parler())  # Appelle la méthode adaptée à chaque type
```

### 2.4 Abstraction
**Définition** :  
L’abstraction consiste à cacher les détails d’implémentation pour ne montrer que l’essentiel. Elle est utilisée avec des classes et des méthodes abstraites (déclarées mais non implémentées).  

**Exemple :**
```python
from abc import ABC, abstractmethod

class Forme(ABC):  # Classe abstraite
    @abstractmethod
    def aire(self):
        pass  # Méthode abstraite

class Rectangle(Forme):
    def __init__(self, largeur, hauteur):
        self.largeur = largeur
        self.hauteur = hauteur

    def aire(self):
        return self.largeur * self.hauteur

rect = Rectangle(5, 10)
print(f"Aire : {rect.aire()}")
```

## 3. Concepts complémentaires

### 3.1 Constructeur et destructeur
- **Constructeur** : Méthode spéciale `__init__` qui initialise les objets lors de leur création.  
- **Destructeur** : Méthode spéciale `__del__` qui est appelée lorsqu’un objet est détruit.  

**Exemple :**
```python
class Exemple:
    def __init__(self):
        print("Objet créé.")

    def __del__(self):
        print("Objet détruit.")

obj = Exemple()
del obj  # Force la destruction de l'objet
```

### 3.2 Méthodes spéciales (ou magiques)
- Ces méthodes commencent et finissent par `__` (double underscore).  
- Elles permettent de définir des comportements spécifiques (par ex. `__str__` pour afficher un objet sous forme de chaîne).  

**Exemple :**
```python
class Personne:
    def __init__(self, nom):
        self.nom = nom

    def __str__(self):
        return f"Personne : {self.nom}"

p = Personne("Alice")
print(p)  # Appelle automatiquement __str__
```

## 4. Avantages de la POO
- **Organisation** : Le code est structuré et lisible.  
- **Réutilisation** : Les classes et méthodes peuvent être réutilisées (héritage).  
- **Maintenance** : Les modifications dans une classe n’affectent pas directement les autres parties du code.  
- **Modélisation réaliste** : Facilite la représentation des concepts du monde réel.

## Conclusion
La POO en Python est un outil puissant pour écrire du code évolutif, maintenable et réutilisable. Pour progresser, pratique ...
