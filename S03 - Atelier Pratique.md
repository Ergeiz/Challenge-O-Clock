# Énoncé
<br/>
## Plan d'addressage 
### Nomenclature
On envisage les adresses 10.0.0.0 pour le lan de Paris, 10.1.0.0 pour celui de Lille, et ainsi de suite pour les autres départements (10.2.0.0, 10.3.0.0, etc.)
Pareil pour le WiFi, mais à partir de 10.110.0.0, de cette facon que ca soit Lan ou WiFi on couvrera tous les départements.
Pour la DMZ et R&D, une adresse en 192.168.0.0/24 pour bien les différencier du lan et wifi, la R&D étant directement relié par fibre à la DMZ
Entre le routeur de PAris et le routeur VPN, un réseau en 92.56.78.0/24
Entre celui de Paris et Lille, un réseau en 92.12.34.0/24
 On va choisir un réseau publique pour le switch où les gens se connecteront au VPN :203.0.113.0/24
