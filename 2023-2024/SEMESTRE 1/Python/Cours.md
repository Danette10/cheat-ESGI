# Scripting Python

## Sommaire

- [Scripting Python](#scripting-python)
  - [Sommaire](#sommaire)
  - [Commentaires](#commentaires)
  - [Types de variables](#types-de-variables)
  - [Affectation et utilisation des variables](#affectation-et-utilisation-des-variables)
  - [Opérateurs](#opérateurs)
  - [Input](#input)
  - [Structures de données](#structures-de-données)
    - [Listes](#listes)
    - [Dictionnaires](#dictionnaires)
    - [Tuples](#tuples)
  - [Print et formatage](#print-et-formatage)
  - [Conditions](#conditions)
  - [Boucles](#boucles)
    - [Boucle for](#boucle-for)
    - [Boucle while](#boucle-while)
  - [Fonctions](#fonctions)
  - [Modules](#modules)
    - [math](#math)
    - [random](#random)
    - [os](#os)
    - [sys et argv](#sys-et-argv)
  - [Fichiers](#fichiers)
    - [Modes de lecture et écriture de fichiers à connaître](#modes-de-lecture-et-écriture-de-fichiers-à-connaître)
  - [Parsing de chaînes de caractères](#parsing-de-chaînes-de-caractères)
  - [Gestion des erreurs (try, except, finally)](#gestion-des-erreurs-try-except-finally)
  - [Threading et parallélisme](#threading-et-parallélisme)
  - [Programmation orientée objet](#programmation-orientée-objet)
    - [Classes](#classes)
    - [Héritage](#héritage)
  - [Exemples de scripts](#exemples-de-scripts)
    - [Calculatrice](#calculatrice)
    - [Ipconfig](#ipconfig)
    - [Générateur de mots de passe avec interface graphique](#générateur-de-mots-de-passe-avec-interface-graphique)
    - [Générateur de mots de passe en ligne de commande](#générateur-de-mots-de-passe-en-ligne-de-commande)
  - [Sources](#sources)
  - [S'exercer en ligne](#sexercer-en-ligne)

## Commentaires

```python
# Ceci est un commentaire sur une ligne
```

```python
"""
Ceci est un commentaire
sur plusieurs lignes
"""
```

## Types de variables

```python
# Entier
a = 1
# Flottant
b = 1.0
# Booléen
c = True
# Chaîne de caractères
d = "Hello World"
```

## Affectation et utilisation des variables

```python
a = 1
b = 2
c = a + b
print(c)
```

## Opérateurs

```python
a = 1
b = 2
c = a + b # Addition
d = a - b # Soustraction
e = a * b # Multiplication
f = a / b # Division
g = a % b # Modulo
h = a ** b # Exponentielle
```

## Input

```python
a = input("Entrez un nombre : ")
print(a)
```

## Structures de données

### Listes

```python
# Création d'une liste
liste = [1, 2, 3, 4, 5]
# Accès à un élément
print(liste[0])
# Ajout d'un élément
liste.append(6)
# Suppression d'un élément
liste.remove(6)
# Parcours d'une liste
for element in liste:
    print(element)
```

### Dictionnaires

```python
# Création d'un dictionnaire
dictionnaire = {"cle1": "valeur1", "cle2": "valeur2"}
# Accès à une valeur
print(dictionnaire["cle1"])
# Ajout d'une valeur
dictionnaire["cle3"] = "valeur3"
# Suppression d'une valeur
del dictionnaire["cle3"]
# Parcours d'un dictionnaire
for cle, valeur in dictionnaire.items():
    print(cle, valeur)
```

### Tuples

```python
# Création d'un tuple
tuple = (1, 2, 3, 4, 5)
# Accès à un élément
print(tuple[0])
# Parcours d'un tuple
for element in tuple:
    print(element)
```

## Print et formatage

```python
a = 1
b = 2
c = a + b
print(f"La somme de {a} et {b} est {c}") # La somme de 1 et 2 est 3
```

## Conditions

```python
age = 18
if age >= 18:
    print("Vous êtes majeur")
elif age < 18:
    print("Vous êtes mineur")
else:
    print("Vous n'avez pas d'âge")
```

## Boucles

### Boucle for

```python
for i in range(10):
    print(i) # Affiche les nombres de 0 à 9
```

### Boucle while

```python
i = 0
while i < 10:
    print(i) # Affiche les nombres de 0 à 9
    i += 1
```

## Fonctions

```python
def addition(a, b):
    return a + b

print(addition(1, 2)) # 3

def afficher():
    print("Hello World")

afficher() # Hello World
```

## Modules

### math

```python
import math

print(math.pi) # 3.141592653589793
```

### random

```python
import random

print(random.randint(0, 10)) # Affiche un nombre aléatoire entre 0 et 10
```

### os

```python
import os

print(os.getcwd()) # Affiche le chemin absolu du dossier courant
```

### sys et argv

```python
import sys

print(sys.argv) # Affiche les arguments passés au script
```

## Fichiers

```python
# Lecture d'un fichier
with open("fichier.txt", "r") as fichier:
    contenu = fichier.read()
    print(contenu)

# Ecriture dans un fichier
with open("fichier.txt", "w") as fichier:
    fichier.write("Hello World")
```

### Modes de lecture et écriture de fichiers à connaître

| Mode | Description |
| --- | --- |
| r | Lecture seule |
| w | Ecriture seule |
| a | Ecriture à la fin du fichier |
| r+ | Lecture et écriture |
| w+ | Lecture et écriture (crée un nouveau fichier si le fichier n'existe pas) |
| a+ | Lecture et écriture (ajoute à la fin du fichier si le fichier existe) |
| ab | Ecrire en mode binaire - ajoute à la fin du fichier si le fichier existe |
| rb | Lire en mode binaire - le fichier doit exister |
| wb | Ecrire en mode binaire - le fichier sera écrasé s'il existe |

## Parsing de chaînes de caractères

```python
chaine = "Hello World"
print(chaine[0]) # H
print(chaine[0:5]) # Hello
print(chaine[6:]) # World
print(chaine[-1]) # d
print(chaine[-5:]) # World
```

```python
chaine = "Hello World"
print(chaine.split(" ")) # ["Hello", "World"]
```

## Gestion des erreurs (try, except, finally)

```python
try: # Code susceptible de générer une erreur
    print(1 / 0)
except ZeroDivisionError: # Erreur de division par zéro
    print("Division par zéro")
finally: # Toujours exécuté
    print("Fin du programme")
```

## Threading et parallélisme

- Un thread est un processus léger qui peut être exécuté en parallèle d'autres threads
- Avantages :
    - Augmentation significative de la vitesse d'exécution pour les tâches lourdes.
    - Meilleure utilisation des ressources du CPU, en particulier sur les architectures multicœurs.
- Inconvénients :
    - Complexité dans la conception d'algorithmes parallèles efficaces.
    - Risques d'incohérence des données et nécessité de synchronisation.
    - Coût élevé en termes de développement et de maintenance du code.
```python
import threading

def afficher():
    print("Hello World")

thread = threading.Thread(target=afficher) # Création du thread
thread.start() # Démarrage du thread
```

## Programmation orientée objet

### Classes

```python
class Personne:
    def __init__(self, nom, prenom):
        self.nom = nom
        self.prenom = prenom

    def afficher(self):
        print(f"Je m'appelle {self.prenom} {self.nom}")

personne = Personne("Doe", "John")
personne.afficher() # Je m'appelle John Doe
```

### Héritage

```python
class Personne:
    def __init__(self, nom, prenom):
        self.nom = nom
        self.prenom = prenom

    def afficher(self):
        print(f"Je m'appelle {self.prenom} {self.nom}")

class Etudiant(Personne):
    def __init__(self, nom, prenom, ecole):
        super().__init__(nom, prenom)
        self.ecole = ecole

    def afficher(self):
        super().afficher()
        print(f"J'étudie à {self.ecole}")

etudiant = Etudiant("Doe", "John", "ECE")
etudiant.afficher() # Je m'appelle John Doe
                    # J'étudie à ECE
```

## Exemples de scripts

### Calculatrice

```python
def addition(a, b):
    return a + b


def soustraction(a, b):
    return a - b


def multiplication(a, b):
    return a * b


def division(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        return "Division par zéro impossible !"


def modulo(a, b):
    return a % b


def exponentielle(a, b):
    return a ** b


def afficher_menu():
    print("---------- Calculatrice ----------")
    print("1. Addition")
    print("2. Soustraction")
    print("3. Multiplication")
    print("4. Division")
    print("5. Modulo")
    print("6. Exponentielle")
    print("7. Quitter")


def calculer(choix):
    if choix == 7:
        print("Au revoir !")
        exit()
    else:
        a = int(input("Entrez le premier nombre : "))
        b = int(input("Entrez le deuxième nombre : "))
        result = "Résultat : "
        if choix == 1:
            result += f"{a} + {b} = {addition(a, b)}"
        elif choix == 2:
            result += f"{a} - {b} = {soustraction(a, b)}"
        elif choix == 3:
            result += f"{a} * {b} = {multiplication(a, b)}"
        elif choix == 4:
            result += f"{a} / {b} = {division(a, b)}"
        elif choix == 5:
            result += f"{a} % {b} = {modulo(a, b)}"
        elif choix == 6:
            result += f"{a} ** {b} = {exponentielle(a, b)}"
        else:
            result = "Choix invalide !"
    print(result)


def main():
    while True:
        afficher_menu()
        choix = int(input("Entrez votre choix : "))
        calculer(choix)


if __name__ == '__main__':
    main()
```

### Ipconfig

```python
import os
import sys


def main():
    if sys.platform == "win32":
        os.system("ipconfig > ipconfig.txt")
    elif sys.platform == "linux":
        os.system("ifconfig > ifconfig.txt")
    else:
        print("OS non supporté")


if __name__ == "__main__":
    main()
```

### Générateur de mots de passe avec interface graphique

```python
import random
import string
import tkinter as tk
import tkinter.messagebox as messagebox
import pyperclip


def generate_password(size):
    char = string.ascii_letters + string.digits + string.punctuation
    password = "".join(random.choice(char) for i in range(size))
    return password


def copy():
    if not password.get():
        messagebox.showerror("Erreur", "Aucun mot de passe à copier")
        return
    pyperclip.copy(password.get())
    messagebox.showinfo("Copie", "Mot de passe copié dans le presse-papier")


def generate():
    if not size.get():
        messagebox.showerror("Erreur", "Aucune taille spécifiée")
        return
    password.set(generate_password(size.get()))


def main():
    global window, password, size
    window = tk.Tk()
    window.title("Générateur de mots de passe")
    window.geometry("300x100")
    window.resizable(False, False)

    password = tk.StringVar()
    size = tk.IntVar()

    tk.Label(window, text="Taille :").grid(row=0, column=0, padx=5, pady=5)
    tk.Entry(window, textvariable=size).grid(row=0, column=1, padx=5, pady=5)
    tk.Button(window, text="Générer", command=generate).grid(row=0, column=2, padx=5, pady=5)

    tk.Label(window, text="Mot de passe :").grid(row=1, column=0, padx=5, pady=5)
    tk.Entry(window, textvariable=password, state="readonly").grid(row=1, column=1, padx=5, pady=5)
    tk.Button(window, text="Copier", command=copy).grid(row=1, column=2, padx=5, pady=5)

    window.mainloop()


if __name__ == "__main__":
    main()
```

### Générateur de mots de passe en ligne de commande

```python
import random
import string
import sys


def generate_password(size):
    char = string.ascii_letters + string.digits + string.punctuation
    password = "".join(random.choice(char) for i in range(size))
    return password


def main():
    size = input("Entrez la taille du mot de passe : ")
    try:
        size = int(size)
    except ValueError:
        print("La taille doit être un nombre entier")
        sys.exit(1)
    if size < 8:
        print("La taille doit être supérieure ou égale à 8")
        sys.exit(1)
    print(generate_password(size))


if __name__ == "__main__":
    main()
```

## Sources

- [https://www.w3schools.com/python/](https://www.w3schools.com/python/)
- [https://docs.python.org/fr/3/](https://docs.python.org/fr/3/)
- [https://www.tutorialspoint.com/python/index.htm](https://www.tutorialspoint.com/python/index.htm)

## S'exercer en ligne

- [https://www.online-python.com/](https://www.online-python.com/)