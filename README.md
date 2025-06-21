# CCMP (Conception et Construction de Compilateurs)

Ce dépôt contient les travaux et ressources pour le cours **Conception et Construction de Compilateurs (CCMP)** dispensé à EPITA, promotion 2027. Il couvre l'ensemble des phases de la conception d'un compilateur, depuis l'analyse lexicale jusqu'à la génération de code machine.

## Table des matières

1. [Présentation du projet](#présentation-du-projet)
2. [Prérequis](#prérequis)
3. [Installation](#installation)
4. [Structure du dépôt](#structure-du-dépôt)
5. [Usage](#usage)
6. [Exercices et TP](#exercices-et-tp)
7. [Contribuer](#contribuer)
8. [Licence](#licence)

## Présentation du projet

Le projet CCMP a pour objectif de mettre en pratique les concepts clés de la traduction de langages :

* **Analyse lexicale** : tokenisation du code source
* **Analyse syntaxique** : construction d’un arbre syntaxique abstrait (AST)
* **Analyse sémantique** : vérification des types, portée, cohérences
* **Génération de code intermédiaire** : trois adresses, quadruplets
* **Optimisation** : analyses de flot, élimination de code mort, registres
* **Génération de code machine** : conversion en assembleur (ARM/x86)

## Prérequis

* Java JDK 11 ou supérieur
* Outils de génération d’automates : `flex` / `jflex`
* Outils de parsing : `bison` / `cup`
* Make / Maven pour l’automatisation des builds
* Connaissances de base en structures de données (listes, tables de hachage, graphes)

## Installation

1. Clonez ce dépôt :

   ```bash
   git clone https://github.com/<votre-utilisateur>/ccmp.git
   cd ccmp
   ```
2. Compilez le projet :

   ```bash
   make
   ```

   ou

   ```bash
   mvn compile
   ```
3. Exécutez les tests de validation :

   ```bash
   make test
   ```

   ou

   ```bash
   mvn test
   ```

## Structure du dépôt

```plaintext
ccmp/
├── lexer/            # Définitions JFlex pour l’analyse lexicale
├── parser/           # Grammaires Cup/Bison et générateurs LR
├── ast/              # Classes Java représentant l’AST
├── semantic/         # Analyse sémantique et tables des symboles
├── ir/               # Generation et représentation du code intermédiaire
├── optimization/     # Passes d’optimisation (DFA, élimination de code mort)
├── target_code/      # Générateurs ARM et x86
├── tests/            # Benchmarks et cas de test Tiger
├── docs/             # Slides, notes de cours et références bibliographiques
└── Makefile / pom.xml
```

## Usage

Pour compiler et analyser un programme Tiger :

```bash
# Compilation lexique+parser
make all

# Exécution du compilateur sur un fichier source
./ccmp src/tests/exemple.tig
```

Pour générer uniquement l’AST ou le code intermédiaire :

```bash
./ccmp --ast src/tests/exemple.tig
./ccmp --ir src/tests/exemple.tig
```

## Exercices et TP

Les répertoires `exercices/` et `tp/` contiennent des énoncés et des squelettes de code pour s’entraîner :

* `exercices/lexical`: tokens et automates
* `exercices/syntaxe`: grammaires LL(1) et LR
* `exercices/semantique`: tables de symboles et vérification de types
* `exercices/ir`: génération de code à trois adresses
* `exercices/optimization`: passes de data-flow

## Contribuer

Les contributions sont les bienvenues !

1. Forkez le dépôt
2. Créez une branche `feature/ma-fonctionnalité`
3. Implémentez votre fonctionnalité ou corrigez un bug
4. Ouvrez une pull request

Merci de respecter la charte de codage Java et d’ajouter des tests unitaires.

## Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
