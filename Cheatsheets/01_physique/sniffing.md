## 1\. Présentation et Contexte d'Utilisation de Wireshark pour le Sniffing

**Wireshark** est un outil open source puissant utilisé pour capturer et analyser le trafic réseau. Il permet de capturer les paquets de données en transit sur un réseau local (LAN) et de les examiner en détail pour diagnostiquer les problèmes, surveiller le trafic, ou même détecter des vulnérabilités. Dans le contexte de la sécurité informatique, Wireshark est souvent utilisé pour simuler des attaques de **sniffing** , où un attaquant intercepte et analyse les données non chiffrées en circulation sur un réseau . Cela peut inclure des informations sensibles comme des identifiants de connexion, des mots de passe, et d'autres données privées. Wireshark est donc un outil indispensable pour les professionnels de la sécurité réseau, les administrateurs système, et les chercheurs en sécurité, afin de mieux comprendre et protéger les flux de données sur un réseau.

## 2\. Commandes Pertinentes pour le Sniffing avec Wireshark

Pour capturer et analyser le trafic réseau avec Wireshark, voici quelques commandes et étapes essentielles :

### 1\. **Capture de Trafic**

Pour capturer du trafic réseau, vous devez d'abord configurer Wireshark pour écouter sur l'interface réseau appropriée. Par exemple, si vous utilisez une interface Ethernet nommée `eth0`, vous pouvez démarrer une capture avec la commande suivante dans la console :

`sudo wireshark -i eth0`

Ou, pour capturer uniquement les paquets de données HTTP, vous pouvez utiliser une expression de filtre :

`sudo wireshark -i eth0 -Y "http"`

### 2\. **Filtres pour Simplifier l'Analyse**

Wireshark offre des filtres très puissants pour filtrer les paquets capturés. Par exemple, pour se concentrer uniquement sur le trafic HTTP, vous pouvez utiliser l'expression de filtre suivante :

`http`

Pour filtrer le trafic SSH :

`ssh`

Pour capturer uniquement le trafic sortant d'une adresse IP spécifique :

`ip.src == 192.168.1.10`

### 3\. **Extraction de Données Sensibles**

Une fois que vous avez capturé du trafic, vous pouvez explorer les paquets individuels pour extraire des informations sensibles. Par exemple, vous pouvez rechercher des paquets contenant des identifiants de connexion ou des mots de passe. Pour cela, vous pouvez utiliser des filtres comme :

`http.request.method == "POST"`

ou

`http contains "password"`

### 4\. **Analyse Avancée avec Information Expert**

Pour simplifier l'analyse de grandes captures de trafic, Wireshark propose l'outil **Information Expert** . Il permet de détecter automatiquement des erreurs ou des anomalies dans le trafic réseau. Pour activer cet outil, vous pouvez utiliser la commande suivante :

Statistics > Conversations > IPv4

Cela vous donnera une vue d'ensemble des conversations IP, facilitant ainsi l'identification des communications suspectes.

## Conclusion

Wireshark est un outil polyvalent qui permet de capturer et d'analyser le trafic réseau avec précision. En utilisant les commandes et filtres appropriés, vous pouvez simuler des attaques de sniffing pour tester la sécurité de votre infrastructure réseau et identifier les failles potentielles. Néanmoins, il est essentiel de respecter la législation locale et d'utiliser Wireshark dans un cadre de test de sécurité autorisé et éthique .
