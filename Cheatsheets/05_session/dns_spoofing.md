# Pentest

## **DNSSPOOF**  
* * *  
- Présentation et contexte d'utilisation de l'outil :

* * *  
dnsspoof est un outil open-source faisant partie de la suite dsniff. Il est utilisé pour effectuer du DNS spoofing, une technique permettant d’usurper les réponses DNS afin de rediriger une cible vers un site frauduleux ou un serveur contrôlé par l’attaquant.  
* * *  
- Commandes pertinentes :

* * *  
Spoof domaintospoof.com pour rediriger vers la machine de l'attaquant :  
```shell  
python dnsspoof.py -r 192.168.0.1 -v 192.168.0.5 -d domaintospoof.com  
```

Spoof toutes les requêtes DNS lookup pour les rediriger vers 80.87.128.67. On peut également utiliser les arguments -t avec -d pour rediriger un domaine spécifique vers une adresse IP spécifique plutôt que vers l'IP de l'attaquant :  
```shell  
python dnsspoof.py -r 192.168.0.1 -v 192.168.0.5 -a -t 80.87.128.67  
```  
* * *  
Explications des différentes arguments :  
* * *  
"-d", "--domain", Choisir le domaine à cibler. Exemple: -d facebook.com

"-r", "--routerIP", Choisir l'IP du routeur. Exemple: -r 192.168.0.1

"-v", "--victimIP", Choisir l'IP de la victime. Exemple: -v 192.168.0.5

"-t", "--redirectto", Argument optionnel pour choisir ou rediriger la requête, par défaut ce sera l'adresse IP local de l'attaquant. Exemple: -t 80.87.128.67")

"-a", "--spoofall", Redirige toutes les requêtes DNS vers l'attaquant ou utiliser l'argument -r pour définir l'ip vers lesquels les rediriger.  
* * *  
- Conclusion  
* * *  
L'outil dnsspoof est un puissant utilitaire permettant de manipuler les réponses DNS dans le cadre de tests d'intrusion. Il est principalement utilisé pour rediriger des requêtes DNS vers une adresse IP définie par l’attaquant.

Grâce aux différentes options disponibles, dnsspoof permet de :  
-Usurper des domaines spécifiques et les rediriger vers une adresse IP malveillante.  
-Intercepter et rediriger toutes les requêtes DNS à des fins d’analyse ou d’attaque.  
-Cibler une victime précise en fonction de son adresse IP.

En conclusion, dnsspoof est un excellent outil pour les pentesters et les auditeurs en cybersécurité, permettant d’évaluer la robustesse des protections DNS et de sensibiliser aux risques liés aux attaques par DNS Spoofing.
