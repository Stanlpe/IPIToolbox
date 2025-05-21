
# ♥ IPI Toolbox ♥ — Boîte à outils Pentest pour l’audit de sécurité

Bienvenue dans **IPI Toolbox**, une boîte à outils interactive en ligne de commande dédiée aux **auditeurs sécurité** et **étudiants en cybersécurité**.  
Ce projet pédagogique permet de sélectionner un **bien essentiel**, un **niveau OSI**, et d’obtenir une **analyse des risques** ainsi qu’une **cheatsheet** pour réaliser l’attaque correspondante.

---

## ❤️ Objectif

- Proposer un outil pédagogique interactif pour apprendre à évaluer les risques liés aux différents éléments du SI.
- Guider l’utilisateur à travers une interface simple à utiliser pour explorer :
  - Les **catégories de biens essentiels**
  - Les **niveaux OSI**
  - Les **risques principaux**
  - Les **impacts en termes de confidentialité, intégrité, disponibilité**
  - Les **méthodes d’attaque** correspondantes via des cheatsheets

---

## 📦 Prérequis

| Outil       | Usage                                 | Installation                   |
|-------------|----------------------------------------|--------------------------------|
| `jq`        | Lecture des fichiers JSON              | `sudo apt install jq`          |
| `curl`      | Récupération distante de cheatsheets   | `sudo apt install curl`        |
| `git`       | Clonage du projet (facultatif)         | `sudo apt install git`         |

📌 **Pourquoi ces outils ?**  
- `jq` permet une extraction simple, modifiable, des données depuis un fichier `.json`.  
- `curl` télécharge les cheatsheets Markdown directement depuis le GitHub.  

---

## 📁 Arborescence du projet

```
IPIToolbox/
├── script_ipi.sh                  # Script Bash interactif
├── data_outils_pentest.json      # Base de données structurée (modifiable)
├── cheatsheets/                  # Cheatsheets techniques par couche OSI
│   ├── 01_physique/
│   ├── 02_liaison/
│   ├── ...
│   └── 07_application/
└── docs/                         # Documentation complémentaire
    ├── INSTALL.md
    └── DATA_MODEL.md
```

---

## 🚀 Installation & Lancement

```bash
git clone https://github.com/ton_user/IPIToolbox
cd IPIToolbox
chmod +x script_ipi.sh
./script_ipi.sh
```

---

## 🧭 Utilisation

Lancement :

```bash
./script_ipi.sh
```

Interface :

```
[♥ IPI ♥] > 
```

Étapes guidées :
1. Choix d’une **catégorie** de bien essentiel
2. Sélection du **bien spécifique**
3. Choix du **niveau OSI concerné**

Résultat affiché :
- 🔐 Risque principal
- ⚠️ Impacts : Confidentialité / Intégrité / Disponibilité
- 📄 Cheatsheet : instructions détaillées pour reproduire ou simuler l’attaque

---

## 📊 Structure du fichier `data_outils_pentest.json`

Le fichier est facilement modifiable pour enrichir la base de données.

```json
{
  "categorie": "Transmission",
  "bien": "Adresses IP et routage réseau (firewalls, routeurs, serveurs)",
  "osi": "3",
  "risque": "Usurpation d’adresse IP ou redirection de trafic",
  "confidentialite": "Fuite potentielle de données réseau",
  "integrite": "Modification non autorisée des règles de routage",
  "disponibilite": "Risque de DoS par empoisonnement ARP",
  "cheatsheet": "03_reseau/usurpation-ip.md"
}
```

Champs :
- `categorie` : Catégorie de bien essentiel
- `bien` : Élément cible
- `osi` : Niveau OSI (1 à 7)
- `risque` : Scénario principal
- `confidentialite`, `integrite`, `disponibilite` : Impacts CIA
- `cheatsheet` : Lien ou chemin vers le fichier Markdown

---

## 📘 Documentation

Tu peux ajouter ou consulter la documentation dans le dossier `docs/` :

- `INSTALL.md` : Instructions détaillées d’installation
- `DATA_MODEL.md` : Explication du format JSON et méthode de contribution

---

## 🧠 À qui s’adresse cet outil ?

- 🧑‍🎓 Étudiants en cybersécurité
- 🕵️ Auditeurs en herbe
- 👨‍🏫 Formateurs en sécurité

---

## 💡 Contribution

- Créer une nouvelle entrée dans `data_outils_pentest.json`
- Ajouter une nouvelle cheatsheet dans le dossier `cheatsheets/[couche]/`
- Pull requests bienvenues !

---

## 🧪 Exemple rapide

```bash
jq '.' data_outils_pentest.json | less
```

---

## 📜 Licence

Projet libre sous licence MIT.

---
