# Introduction à la cryptographie

## Sommaire

- [Introduction à la cryptographie](#introduction-à-la-cryptographie)
  - [Sommaire](#sommaire)
  - [Définitions](#définitions)
  - [Chiffrement de Vigenère](#chiffrement-de-vigenère)
  - [Chiffrement de Vernam (Masque jetable)](#chiffrement-de-vernam-masque-jetable)
  - [Chiffrement par Transposition](#chiffrement-par-transposition)
  - [Chiffrement par Substitution](#chiffrement-par-substitution)
  - [Chiffrement de César](#chiffrement-de-césar)
  - [Chiffrement Symétrique](#chiffrement-symétrique)
  - [Chiffrement Asymétrique](#chiffrement-asymétrique)
  - [Histoire de la Cryptographie](#histoire-de-la-cryptographie)
  - [Concepts Fondamentaux](#concepts-fondamentaux)

## Définitions

**Cryptographie** :
- La science de la communication sécurisée en présence d'adversaires.
- La cryptographie est utilisée pour assurer la confidentialité, l'authenticité, l'intégrité et la non-répudiation des données.

*Objectif* : garantir la « sécurité » des communications malgré la présence
d’attaquants extérieurs.

**Cryptanalyse** :
- La science de la découverte de la clé secrète d'un cryptosystème.
- La cryptanalyse est utilisée pour casser les systèmes de chiffrement et les protocoles cryptographiques.

**Cryptologie** :
- La science de la cryptographie et de la cryptanalyse.


## Chiffrement de Vigenère

**Principe détaillé** : 
- Chiffrement poly-alphabétique basé sur l'utilisation d'une clé de mots ou de phrases. 
- La clé est répétée pour correspondre à la longueur du message. 
- Chaque lettre du message est décalée selon la position de la lettre correspondante de la clé dans l'alphabet.

<span style='color: #229948'>**Exemple développé**</span> : 

>**Clé** : <span style='color: #f4bfbf'>CHIPS</span>
>
>**Message** : <span style='color: #bce4f5'>I L E S T C A C H E A P A R I S</span>
>
>**Message chiffré** : K S M H L E H K W W C W I G A U
>
><div style="text-align:center">
><img src='images/Vigenère.png' alt="Vigenère">
></div>

## Chiffrement de Vernam (Masque jetable)

**Principe détaillé** : 
- Un chiffrement où chaque bit ou caractère du message est combiné (souvent via une opération XOR) avec un bit ou caractère d'une clé secrète, aléatoire, et de même longueur que le message. 
- Le chiffrement est théoriquement incassable si la clé est vraiment aléatoire, gardée secrète, et utilisée une seule fois.

<span style='color: #229948'>**Exemple développé**</span> :  
>**Message** : 101001011101
>
>**Clé** : 011101100100
>
>**Message chiffré** : Chiffrement par XOR → 110100111001.

## Chiffrement par Transposition

**Principe détaillé** : 
- Le texte est écrit selon un certain ordre ou schéma, puis les lettres sont transposées selon une règle prédéfinie. 
- Ce type de chiffrement conserve la fréquence des lettres mais change leur ordre.

<span style='color: #229948'>**Exemple développé**</span> : 
>*Scytale* 
>- Le message est écrit sur une bande enroulée autour d'un bâton. 
>- La lecture se fait après avoir enroulé la bande autour d'un bâton de même diamètre.

## Chiffrement par Substitution

**Principe détaillé** :
- Chaque lettre (ou groupe de lettres) dans le message est systématiquement remplacée par une autre lettre (ou symbole, chiffre, etc.). 
- La substitution peut être fixe (comme dans le chiffrement de César) ou plus complexe (comme dans le chiffre des Templiers).

<span style='color: #229948'>**Exemple développé**</span> : 
>**_Chiffre des Templiers_** 
>
>Chaque lettre est remplacée par un symbole unique. Par exemple, "A" peut être remplacé par un triangle, "B" par un carré, etc.
>

## Chiffrement de César

**Principe détaillé** :

Chaque lettre est remplacée par une autre lettre, selon un décalage fixe. Par exemple, si le décalage est de 3, "A" devient "D", "B" devient "E", etc.

<span style='color: #229948'>**Exemple développé**</span> : 
>**Décalage** : 3
>
>**Message** : <span style='color: #bce4f5'>Demandez le retrait des troupes</span>
>
>**Message chiffré** : <span style='color: #f4bfbf'>Ghpdqghc oh uhwudlw ghv wurxshv</span>

## Chiffrement Symétrique

**Détails** : 
- Utilise une seule clé pour le chiffrement et le déchiffrement. 
- Efficace en termes de calcul, mais le partage de clé est un défi majeur. 
- Les algorithmes comme AES utilisent des combinaisons complexes de permutations, substitutions, et opérations de mélange pour assurer la sécurité.

**Exemples d'algorithmes** : AES (Advanced Encryption Standard), DES (Data Encryption Standard).

## Chiffrement Asymétrique

**Détails** : 
- Implique l'utilisation de deux clés liées mathématiquement → une clé publique et une clé privée. 
- La clé publique peut être partagée librement, tandis que la clé privée doit rester secrète. 
- Utilisé pour la signature numérique et le chiffrement de données.

**Exemple d'application** : Les échanges sécurisés sur Internet, comme les transactions bancaires en ligne.

## Histoire de la Cryptographie

1. **Âge artisanal** : Techniques simples, souvent basées sur des méthodes de substitution et transposition.
2. **Âge technique** : Développement de machines de chiffrement comme Enigma pendant la Seconde Guerre mondiale.
3. **Âge paradoxal** : Cryptographie moderne avec des algorithmes complexes et sécurisés, adaptés à l'ère numérique.

## Concepts Fondamentaux

**Confusion et Diffusion (Shannon)** : 
- Stratégies pour assurer la sécurité d'un cryptosystème. 
- La confusion vise à rendre la relation entre la clé et le chiffre aussi complexe que possible, tandis que la diffusion vise à dissiper les statistiques du texte clair dans le texte chiffré.

**Principe de Kerckhoffs** : 
- Un système cryptographique doit rester sécurisé même si tout est connu à son sujet à l'exception de la clé secrète.