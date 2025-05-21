# ♥ IPI Toolbox ♥ — Boîte à outils Pentest pour l’audit de sécurité

Bienvenue dans **IPI Toolbox**, une boîte à outils interactive en ligne de commande dédiée aux **auditeurs sécurité** et **étudiants en cybersécurité**.  
Ce projet pédagogique permet de sélectionner un **bien essentiel**, un **niveau OSI**, et d’obtenir une **analyse des risques** ainsi qu’une **cheatsheet** pour réaliser l’attaque correspondante.

---

## 🧱 Démarche de réalisation

Ce projet s’inscrit dans une logique d’**audit de sécurité offensive**. L’objectif est de proposer une interface permettant à un auditeur ou apprenant :

1. D’**identifier les biens essentiels à l'organisation**
2. De les **classifier selon leur exposition dans le modèle OSI**
3. De **lister les risques métier associés (confidentialité, intégrité, disponibilité)**
4. D’obtenir une **fiche d’attaque (cheatsheet)** adaptée

Les données sont structurées dans un fichier `JSON` généré depuis un tableau Excel.  
Chaque attaque est liée à une couche OSI et décrite dans un fichier Markdown, accessible depuis l’interface.

---

## 📘 Notice d’utilisation

### 1. Installation des dépendances

- Bash ≥ 4.0
- jq (`sudo apt install jq`)
- curl (`sudo apt install curl`)

### 2. Lancer l’outil

```bash
chmod +x script_ipi.sh
./script_ipi.sh
