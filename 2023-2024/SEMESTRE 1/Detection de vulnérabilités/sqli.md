# Injections SQL

## Sommaire
- [Injections SQL](#injections-sql)
  - [Sommaire](#sommaire)
  - [Définition](#définition)
  - [Impact](#impact)
  - [Les différents types d'injections SQL](#les-différents-types-dinjections-sql)
  - [Les données faciles à chercher](#les-données-faciles-à-chercher)
  - [Les principaux type d'exploitation](#les-principaux-type-dexploitation)
    - [Error-based](#error-based)
    - [Union-based](#union-based)
    - [Blind](#blind)
  - [Prévention](#prévention)


## Définition

*Une injection SQL est une technique d'exploitation d'une faille d'une application interagissant avec une base de données, en injectant une requête SQL non prévue par le système et pouvant compromettre sa sécurité.*

## Impact

- Récupération de données sensibles stockées dans la base de données (identifiants, mots de passe, informations personnelles, etc.)
- Contournement des formulaires de connexion
- Modification des données stockées dans la base de données (ajout, suppression, modification)
- Suppression de la base de données
- Lécture et écriture sur le système de fichiers (droits "FILE")
- Exécution de commandes à distance (Webshell ou xp_cmdshell)

## Les différents types d'injections SQL

- in-band : l'attaquant utilise la même voie de communication que la victime (ex: requête SQL et réponse HTTP)
- out-of-band : l'attaquant utilise une voie de communication différente de celle de la victime (ex: requête SQL et email)
- inferentielle : pas de données directement extraites mais déduites d'un comportement (ex: temps de réponse)

## Les données faciles à chercher

- **@@version** : version du SGBD
- **user()** : utilisateur connecté à la base de données
- **current_user()** : utilisateur connecté à la base de données
- **database()** : base de données courante
- **@@hostname** : nom de la machine

## Les principaux type d'exploitation

- **Error-based** : cherche à provoquer une erreur SQL
- **Union-based** : complète la requête originale
- **Blind** : pas de réponse directe de la base de données
- **Stacked queries** : exécution de plusieurs requêtes

### Error-based

- L'objectif est de provoquer une erreur SQL pour récupérer des informations
- La sous-requête est résolue et provoque une erreur dans la requête principale
- Le résultat de l'erreur est affiché dans le message d'erreur

```sql
SELECT id, name, firstname FROM users WHERE id = 1' UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15 FROM information_schema.tables -- -
```
→ Erreur : *The used SELECT statements have a different number of columns*

### Union-based

- L'objectif est de compléter la requête originale pour récupérer des informations
- La sous-requête est résolue et ajoutée à la requête principale
- Il faut que le nombre de colonnes soit identique dans les deux requêtes

ℹ️ Pour connaître le nombre de colonnes, on peut utiliser la fonction **ORDER BY** avec un nombre de colonnes croissant jusqu'à obtenir une erreur

```sql
...id = 1' ORDER BY 5-- -
```
→ Pas de réponse, c'est moins

```sql
...id = 1' ORDER BY 4-- -
```
→ Réponse, c'est plus ou égal

### Blind

- L'objectif est de récupérer des informations sans réponse directe de la base de données
- Vérifier si une condition est vraie ou fausse
- Utilisation de la fonction **IF** ou **CASE** pour afficher un résultat différent selon la condition

```sql
...id = 1' AND IF(SUBSTR((SELECT current_user()),1,1)='r',SLEEP(5),1)-- -
```
→ Si la première lettre de l'utilisateur est "r", alors attendre 5 secondes

## Prévention

- Utiliser des requêtes préparées
- Utiliser des fonctions de nettoyage des données
- Utiliser les ORM (Object Relational Mapping) des frameworks de développement web (ex: Doctrine pour Symfony)