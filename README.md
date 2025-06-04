
# 🧰 IPI Toolbox – Pentest

## 📑 Sommaire

- [🎯 Présentation](#-présentation)
- [🛠️ Fonctionnalités](#️-fonctionnalités)
- [📦 Installation](#-installation)
- [🚀 Utilisation](#-utilisation)
- [🧪 Choix technologiques](#-choix-technologiques)
- [📁 Structure du dépôt](#-structure-du-dépôt)
- [📚 Documentation](#-documentation)
- [📸 Démonstration](#-démonstration)
- [🤝 Contribuer](#-contribuer)
---

## 🎯 Présentation

**IPI Toolbox** est une boîte à outils interactive en ligne de commande développée dans un cadre pédagogique.  
Elle vise à sensibiliser à la cybersécurité en combinant :

- Les fondamentaux de la sécurité informatique (confidentialité, intégrité, disponibilité)
- Une approche structurée autour du modèle OSI (Open Systems Interconnection)
- Des scénarios concrets d’attaques documentés via des cheatsheets

🎓 L’utilisateur choisit un **La catégorie ainsi que le bien essentiel associé** et un **niveau OSI ciblé**, puis accède :
- Aux **risques correspondants**
- À une **fiche d’attaque représentative**
- Et aux **outils de pentest associés**

---

## 🛠️ Fonctionnalités

- ✅ Interface CLI simple et interactive  
- 🎯 Sélection guidée de biens essentiels à protéger  
- 🌐 Parcours structuré par couche OSI  
- 🔐 Analyse des risques selon la triade CIA  
- 📘 Cheatsheets claires pour chaque type d’attaque  
- 📂 Organisation modulaire et évolutive  

---

## 📦 Installation

✅ Prérequis système

Vous devez disposer :

- d’un environnement Linux
- d’un accès internet (pour cloner ou télécharger les cheatsheets)
- de droits d’exécution dans le dossier cloné

---

🧰 Dépendances nécessaires

| Outil       | Usage                                 | Installation                   |
|-------------|----------------------------------------|--------------------------------|
| `jq`        | Lecture des fichiers JSON              | `sudo apt install jq`          |
| `curl`      | Récupération distante de cheatsheets   | `sudo apt install curl`        |
| `git`       | Clonage du projet (facultatif)         | `sudo apt install git`         |


Cloner le dépôt Git
```bash
git clone https://github.com/Stanlpe/IPIToolbox.git
```
Accéder au répertoire de l'outil
``` 
cd IPIToolbox
```
Rendre le script exécutable
```
chmod +x ipi_pentest.sh
```

## 🧪 Choix technologiques

Ce projet mise sur des technologies simples, accessibles et robustes :

### 🐚Script Bash

-   Portabilité universelle sur les systèmes UNIX
    
-   Facilité d’usage en TP ou environnement contraint
    
-   Interaction directe avec l’utilisateur
    

### 📁 Data model en .JSON

-   Stockage structuré des attaques et métadonnées
    
-   Lisible et extensible
    

### 📝 Cheatsheets Markdown

-   Format des cheatsheets
    
-   Parfait pour GitHub, simple à éditer et lire
    

🎯 Ces choix garantissent un outil **léger**, **portable** et **pédagogique**.

----------

## 📁 Structure du dépôt

```plaintext
IPIToolbox/
├── Cheatsheets/              # Fiches d’attaques par couche OSI
│   └── 03_Reseau_test.md
├── Docs/                     # Documentation interne du projet
├── data_outils_pentest.json  # Base de données structurée (risques & attaques)
├── ipi_pentest.sh            # Script principal CLI
└── README.md                 # Fichier de présentation
```


----------


## 📚 Documentation

La documentation du projet se trouve dans le dossier `Docs/` :

-   [`INSTALL.md`](Docs/INSTALL.md) : instructions détaillées d’installation et configuration de l’outil dans un environnement Linux.
    
-   [`DATA_MODEL.md`](Docs/DATA_MODEL.md) : spécifie le format du fichier `data_outils_pentest.json` (structure, champs, exemples).
    

### 🧠 Cheatsheets

Les fichiers du dossier `Cheatsheets/` décrivent des attaques classées par couche OSI, avec pour chacune :

-   Une **description de l’attaque**
    
-   Le **niveau OSI concerné**
    
-   Les **risques liés**
    
-   Des **outils de pentest** associés (quand c’est pertinent)
    

🧩 Ces documents servent à illustrer les risques sur chaque couche réseau de manière pédagogique et pratique.
  

----------

## ▶️ Utilisation du script `ipi_pentest.sh`

Le script peut être exécuté de deux manières :

### 1. 🔧 Mode interactif classique

L'utilisateur répond manuellement aux questions successives :

```bash
./ipi_pentest.sh

1. Choix de la catégorie de bien essentiel

![Interface](https://i.ibb.co/M5MmbsHb/image.png
)


2. Choix du bien essentiel

![Interface](https://i.ibb.co/xqbL6BRG/image.webp
)

3. Choix du niveau OSI

![Interface](https://i.ibb.co/d08Bdfvs/image.png
)

4. Résultat

   
![Interface](https://i.ibb.co/tpHJfX1m/image.webp
)
----------

## 2. 🤖 Mode automatisé avec fichier d'entrée

Le script `ipi_pentest.sh` peut être exécuté automatiquement à partir d’un fichier d’entrée. Cela permet de simuler une session interactive sans intervention humaine, ce qui est utile pour les démonstrations, les tests ou l'intégration dans des processus automatisés.

### ▶️ Commande

```bash
./ipi_pentest.sh < Input/input_bdd
```

Ici, Input/input_bdd est un fichier texte contenant les réponses attendues par le script.

📄 Exemple de contenu du fichier Input/input_bdd :
```
4
1
7
```

Chaque ligne correspond à une réponse dans l’ordre :

```
1. Catégorie de bien essentiel (Données chiffrées sensibles)
2. Bien essentiel concernée (Base de données)
3. Niveau OSI (7)
```

## 📁 À propos du dossier `Input/`

Le dossier `Input/` contient des fichiers texte préremplis représentant différents cas d’usage. Ces fichiers peuvent être utilisés pour :

- lancer des démonstrations automatisées,
- tester le comportement du script sans interaction,

🛠️ Ces fichiers peuvent être modifiés ou enrichis en fonction des besoins. Chaque fichier doit contenir une réponse par ligne selon l’ordre attendu par le script.



## 🤝 Contribuer

Les contributions sont les bienvenues !
