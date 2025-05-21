## **MACChanger**  
* * *  
- Présentation et contexte d'utilisation de l'outil :

* * *  
MACChanger est un outil en ligne de commande open-source principalement utilisé sous Linux pour effectuer du MAC Spoofing. Cette technique permet de modifier l'adresse MAC d'une carte réseau afin d’usurper l'identité d'un autre périphérique sur un réseau.

Cas d’utilisation du Mac Spoofing avec MACChanger :  
-Évasion des filtrages MAC : Certains réseaux restreignent l’accès aux appareils autorisés via un filtrage d’adresse MAC.  
-Interception de trafic : En usurpant l’adresse MAC d’un périphérique actif, il est possible d’intercepter son trafic.  
-Éviter la détection réseau : Un attaquant peut masquer son identité en utilisant une autre adresse MAC.  
* * *  
- Commandes pertinentes :  
* * *  
1. Vérifier l'adresse MAC actuelle

Avant de modifier l'adresse MAC, il est important de vérifier l'adresse MAC actuelle de l'interface réseau. Cela peut être effectué avec la commande :

```shell  
ifconfig eth0  
```  
Cela affichera l'adresse MAC actuelle de l'interface eth0.

2. Changer l'adresse MAC

MACChanger offre plusieurs options pour modifier l'adresse MAC d’une interface réseau. Voici quelques commandes courantes :

Générer une adresse MAC aléatoire :  
```shell  
sudo macchanger -r eth0  
```  
Cela génère une adresse MAC aléatoire et l’applique à l’interface eth0.

Changer manuellement l'adresse MAC :

```shell  
sudo macchanger -m 00:11:22:33:44:55 eth0  
```  
Cela change l’adresse MAC de l’interface eth0 pour 00:11:22:33:44:55.

Réinitialiser l'adresse MAC à la valeur d’usine :  
```shell  
sudo macchanger -p eth0  
```

Cela réinitialise l’adresse MAC de l’interface eth0 à son adresse d’usine.

3. Vérifier le changement d'adresse MAC  
Après avoir modifié l'adresse MAC, il est conseillé de vérifier que le changement a bien été effectué. Utilise la commande suivante pour afficher les détails de l'interface réseau :

```shell  
ifconfig eth0  
```  
L’adresse MAC affichée doit être celle que tu viens de définir.

Explication des options et arguments importants :  
-r Génère une adresse MAC aléatoire et l’applique à l’interface.  
-m Définit une adresse MAC spécifique (ex. 00:11:22:33:44:55).  
-p Réinitialise l’adresse MAC de l’interface à sa valeur d’origine.  
-A Affiche une adresse MAC aléatoire dans une plage spécifique (option avancée).  
-s Permet de spécifier un format de MAC particulier (par exemple, format 3 octets spécifique).  
* * *  
- Conclusion  
* * *  
MACChanger est un outil puissant permettant de changer une adresse MAC afin de contourner certaines restrictions réseau ou d’effectuer des attaques MITM. Il offre une interface intuitive pour modifier les adresses MAC et intercepter du trafic réseau.

En pentest, il est utile pour tester la robustesse des mesures de protection contre les attaques Mac Spoofing et sensibiliser aux bonnes pratiques de cybersécurité.
