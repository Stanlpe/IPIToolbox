
# 🛠️ IPI Toolbox — Boîte à outils de Pentest Interactive

Bienvenue dans **IPI Toolbox**, une boîte à outils interactive en ligne de commande dédiée aux auditeurs sécurité et étudiants en cybersécurité.

Ce projet pédagogique vous permet de sélectionner un **bien essentiel**, un **niveau OSI**, et d’obtenir :
- une **analyse des risques** (confidentialité, intégrité, disponibilité),
- une **cheatsheet** associée expliquant comment réaliser une attaque représentative.

---

## 🎯 Objectifs & Démarche

Le projet a été conçu avec une double visée :
1. **Pédagogique** : permettre aux utilisateurs de comprendre l’impact des attaques selon les niveaux OSI.
2. **Opérationnelle** : fournir des outils pratiques et concrets pour réaliser des tests d’intrusion ciblés.

La base de données (`data_outils_pentest.json`) a été construite à partir d’un tableur de classification (`analyse.xlsx`), recensant :
- des **catégories de biens essentiels**,
- les **éléments techniques associés**,
- les **couches OSI impactées**,
- les **risques sécurité correspondants**.

---

## 🧠 Structure de l’outil

- `ipi_pentest.sh` : interface interactive
- `data_outils_pentest.json` : base de connaissance modifiable
- `cheatsheets/` : ensemble de fiches pratiques classées par couche OSI 
- `docs/` : documentations (installation, structure, tableur, etc.)

---

## 🔗 Accès aux Cheatsheets

Les cheatsheets sont organisées par couche OSI :

Chacune explique comment effectuer une attaque courante sur la couche choisie, avec outils, commandes et exemples.

---

## 📊 Notice de classification du tableur `analyse.xlsx`

Le tableur contient 3 sections clés :
- **Catégories de biens essentiels** (ex : Transmission, Identité…)
- **Biens essentiels concernés** (ex : DNS, IP, Adresses MAC…)
- **Risques associés** selon les principes CID (Confidentialité, Intégrité, Disponibilité)

💡 Utilisation :
- Ajouter ou éditer une ligne pour enrichir la base
- Exporter les données en JSON pour alimenter `data_outils_pentest.json`


---

## 🚀 Lancer l’outil

```bash
chmod +x ipi_pentest.sh
ipi_pentest.sh
```

---

## 📚 Documentation

- [INSTALL.md](Docs/INSTALL.md)
- [DATA_MODEL.md](Docs/DATA_MODEL.md)

---

## 🤝 Contributions

Contributions bienvenues pour enrichir les cheatsheets, structurer d’autres niveaux OSI ou proposer de nouveaux scénarios d’attaque.

---

## 🧑‍💻 Auteur

Ce projet a été réalisé dans le cadre d’un apprentissage en cybersécurité. Il constitue un **exercice pratique de modélisation des risques**.

---
