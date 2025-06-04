
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

Cloner le dépôt Git
```bash
git clone https://github.com/Stanlpe/IPIToolbox.git
```
Accéder au répertoire de l'outil
``` 
cd IPIToolbox
```
Donner les droits d'exécution au script Bash
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

## 📁 Structure du dépôt

```plaintext
IPIToolbox/
├── Cheatsheets/              # Fiches d’attaques par couche OSI
│   └── 03_Reseau_test.md
├── Docs/                     # Documentation interne du projet
│   └── structure_fichiers.md
├── data_outils_pentest.json  # Base de données structurée (risques & attaques)
├── ipi_pentest.sh            # Script principal CLI
└── README.md                 # Fichier de présentation
```


----------


## 📚 Documentation

La documentation du projet se trouve dans le dossier `Docs/` :

-   [`INSTALL.md`](Docs/INSTALL.md) : instructions détaillées d’installation et configuration de l’outil dans un environnement Linux.
    
-   [`DATA_MODEL.md`](Docs/DATA_MODEL.md) : spécifie le format du fichier `data_outils_pentest.json` (structure, champs, exemples).
    
-   `structure_fichiers.md` : explique l’organisation logique du dépôt, le nommage des cheatsheets, et les relations entre couches OSI et biens essentiels.
    

### 🧠 Cheatsheets

Les fichiers du dossier `Cheatsheets/` décrivent des attaques classées par couche OSI, avec pour chacune :

-   Une **description de l’attaque**
    
-   Le **niveau OSI concerné**
    
-   Les **risques liés**
    
-   Des **outils de pentest** associés (quand c’est pertinent)
    

🧩 Ces documents servent à illustrer les risques sur chaque couche réseau de manière pédagogique et pratique.
  

----------

📸 Démonstration

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

## 🤝 Contribuer

Les contributions sont les bienvenues !
