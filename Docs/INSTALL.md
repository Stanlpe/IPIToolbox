# ⚙️ INSTALLATION & PRÉREQUIS

Ce fichier décrit les éléments nécessaires pour utiliser correctement **IPI Pentest Toolbox**, ainsi que les étapes d’installation et de configuration.

---

## ✅ Pré-requis

| Outil / Dépendance | Rôle | Installation |
|--------------------|------|--------------|
| `bash`             | Exécution du script interactif | Présent nativement sur Linux/Mac |
| `jq`               | Lecture des fichiers `.json` | `sudo apt install jq` |
| `curl`             | Téléchargement de cheatsheets GitHub | `sudo apt install curl` |
| `git` *(optionnel)*| Clonage du dépôt GitHub | `sudo apt install git` |

---

## ❓ Pourquoi ces prérequis ?

- **`bash`** : Le cœur de l’interface interactive est un script shell.
- **`jq`** : Permet d'extraire les informations pertinentes du fichier `.json`.
- **`curl`** : Sert à télécharger les cheatsheets automatiquement depuis GitHub.
- **`git`** : Utile pour cloner le projet localement.

---

## 📥 Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/<ton_user>/IPIToolbox.git
cd IPIToolbox

