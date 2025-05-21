
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
  "cheatsheet": {
    "url": "URL GitHub brute vers le fichier .md",
    "description": "Brève explication du contenu de la cheatsheet"
  }
}
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
  "cheatsheet": {
    "url": "https://raw.githubusercontent.com/ton_user/IPIToolbox/main/OSI3/nmap_scan.md",
    "description": "Utiliser nmap pour scanner les IP et détecter les routes"
  }
}
```

---

## 🛠️ Conseils de modification

- Vous pouvez modifier ou ajouter des entrées avec un éditeur JSON comme [JSONLint](https://jsonlint.com).
- Le champ `osi_layer` doit être un entier sous forme de chaîne (`"1"` à `"7"`).
- L’URL vers les cheatsheets doit pointer vers un fichier brut sur GitHub
