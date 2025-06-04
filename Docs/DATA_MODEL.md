
# 📊 DATA_MODEL — Structure des données JSON

Ce document décrit la structure du fichier `data_outils_pentest.json` utilisé par **IPI Toolbox** pour associer les biens essentiels aux couches OSI, aux risques et aux cheatsheets.

---

## 📁 Fichier concerné

```bash
data_outils_pentest.json
```

---

## 🧬 Structure du JSON

Chaque entrée du fichier est structurée comme suit :

```json
{
  "categorie": "Nom de la catégorie de bien essentiel",
  "bien_essentiel": "Nom du bien essentiel",
  "osi_layer": "Nom de la couche OSI (1 à 7)",
  "risques": {
    "confidentialite": "Description ou niveau de risque",
    "integrite": "Description ou niveau de risque",
    "disponibilite": "Description ou niveau de risque"
  },

```

---

## 📌 Exemple

```json
{
  "categorie": "Transmission",
  "bien_essentiel": "Adresses IP et routage réseau (firewalls, routeurs, serveurs)",
  "osi_layer": "3",
  "risques": {
    "confidentialite": "Modérée",
    "integrite": "Élevée",
    "disponibilite": "Critique"
  },
```

---

## 🛠️ Conseils de modification
- Respectez l’orthographe des noms de catégories et de biens essentiels pour assurer la cohérence avec l’interface IPI Toolbox.
- Le champ `osi_layer` doit être un entier sous forme de chaîne (`"1"` à `"7"`).
- Utilisez un éditeur de texte avec coloration syntaxique JSON (ex. VSCode, Sublime Text) pour éviter les erreurs de formatage.
- Vérifiez la validité du fichier JSON avec un outil comme https://jsonlint.com avant de l’importer dans IPI Toolbox.

