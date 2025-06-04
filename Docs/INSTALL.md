
# 📦 INSTALLATION — IPI Toolbox

Ce fichier vous guide étape par étape dans l’installation et l’utilisation de **IPI Toolbox**, une boîte à outils interactive pour auditeurs et étudiants en cybersécurité.

---

## ✅ Prérequis système

Vous devez disposer :

- d’un environnement Linux
- d’un accès internet (pour cloner ou télécharger les cheatsheets)
- de droits d’exécution dans le dossier cloné

---

## 🧰 Dépendances nécessaires

| Outil       | Usage                                 | Installation                   |
|-------------|----------------------------------------|--------------------------------|
| `jq`        | Lecture des fichiers JSON              | `sudo apt install jq`          |
| `curl`      | Récupération distante de cheatsheets   | `sudo apt install curl`        |
| `git`       | Clonage du projet (facultatif)         | `sudo apt install git`         |

---

## 💾 Clonage du dépôt

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


---


## 🚀 Exécution du script

```bash
./ipi_pentest.sh
```

Vous accédez alors à une interface intuitive :

[
![Interface](https://i.ibb.co/nXXtb0K/image.png
)


---

## 🆘 Problèmes fréquents

- ❗ `command not found: jq` → installez jq : `sudo apt install jq`
- ❗ `Permission denied` → vérifiez que le script a les droits : `chmod +x sipi_pentest.sh`
- ❗ Le script ne se lance pas → assurez-vous d’être dans le bon dossier et sur un système Linux

---

## 🧪 Test rapide

```bash
jq '.' data_outils_pentest.json | less
```

Permet de vérifier que le fichier de données est lisible.

---
