## Ettercap pour Faire du Man-in-the-Middle (MITM)

### Présentation et Contexte d'Utilisation

**Ettercap** est un outil puissant et versatile utilisé pour effectuer des attaques de type Man-in-the-Middle (MITM) dans les réseaux locaux (LAN). Il permet d'intercepter et d'analyser le trafic réseau, de réaliser des attaques de poisson d'ARP (ARP poisoning), et d'effectuer diverses autres actions sur le trafic réseau. Ettercap est particulièrement utile pour tester la sécurité des réseaux et identifier les vulnérabilités potentielles .

Dans le cadre d'une attaque MITM, Ettercap peut être utilisé pour intercaler entre deux hôtes sur un réseau, capturer et analyser le trafic en transit, et même modifier ce trafic pour rediriger les utilisateurs vers des sites frauduleux ou extraire des informations sensibles comme des mots de passe. Cela est souvent réalisé en utilisant des techniques comme l'usurpation ARP (ARP poisoning) ou l'usurpation DNS (DNS spoofing) .

### Techniques et Attaques MITM avec Ettercap

#### 1\. **Poisonning ARP (ARP Spoofing)**

L'usurpation ARP est une technique couramment utilisée pour réaliser des attaques MITM. Elle consiste à envoyer des faux messages ARP pour faire croire à deux machines sur un réseau que l'attaquant est l'une des deux. Cela permet à l'attaquant de se positionner entre les deux machines et de capturer le trafic en transit .

**Usage :** Pour réaliser une attaque de poisson d'ARP avec Ettercap, vous pouvez utiliser la commande suivante :

`ettercap -T -Q -M arp:remote // <victime> // <routeur>`

Par exemple, pour intercaler entre une victime (`192.168.1.100`) et un routeur (`192.168.1.1`), vous pouvez utiliser :

`ettercap -T -Q -M arp:remote // 192.168.1.100 // 192.168.1.1`

#### 2\. **Usurpation DNS (DNS Spoofing)**

L'usurpation DNS consiste à rediriger les requêtes DNS des utilisateurs vers des serveurs DNS contrôlés par l'attaquant. Cela permet de rediriger les utilisateurs vers des sites frauduleux, où leurs informations peuvent être volées .

**Usage :** Pour réaliser une attaque de DNS spoofing avec Ettercap, vous pouvez utiliser le plugin `dns_spoof` :

`ettercap -T -Q -M arp:remote // <victime> // <routeur> --plugin dns_spoof`

Par exemple, pour intercaler entre une victime (`192.168.1.100`) et un routeur (`192.168.1.1`) et rediriger les requêtes DNS, vous pouvez utiliser :

`ettercap -T -Q -M arp:remote // 192.168.1.100 // 192.168.1.1 --plugin dns_spoof`

#### 3\. **Capture de Mots de Passe HTTP**

Ettercap peut également être utilisé pour capturer des mots de passe HTTP en transit. Cela est souvent réalisé en combinant des plugins comme `http_passwords` avec des techniques de poisson d'ARP.

**Usage :** Pour capturer des mots de passe HTTP, vous pouvez utiliser les commandes suivantes :

`ettercap -T -Q -M arp:remote // <victime> // <routeur> --plugin http_passwords`

Par exemple, pour intercaler entre une victime (`192.168.1.100`) et un routeur (`192.168.1.1`) et capturer des mots de passe HTTP, vous pouvez utiliser :

ettercap -T -Q -M arp:remote // 192.168.1.100 // 192.168.1.1 --plugin http_passwords

### Conclusion

Ettercap est un outil puissant et flexible pour réaliser des attaques MITM et analyser le trafic réseau. Il permet de capturer et d'analyser divers types de trafic, d'intercaler entre les hôtes sur un réseau, et de réaliser des attaques sophistiquées comme l'usurpation ARP et l'usurpation DNS. Il est essentiel de respecter la législation locale et d'utiliser Ettercap dans un cadre de test de sécurité autorisé et éthique .
