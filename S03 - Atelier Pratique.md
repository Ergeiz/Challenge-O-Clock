
# Plan d'addressage  
## Nomenclature  
On envisage les adresses `10.0.0.0/22` pour le lan de Paris, `10.1.0.0/22` pour celui de Lille, et ainsi de suite pour les autres départements (`10.2.0.0/22`, `10.3.0.0/22`, etc.)  
Pareil pour le WiFi, mais à partir de `10.110.0.0/22`, de cette facon que ca soit Lan ou WiFi on couvrera tous les départements.  
Pour la DMZ et R&D, une adresse en `192.168.0.0/24` pour bien les différencier du lan et wifi, la R&D étant directement relié par fibre à la DMZ  
Entre le routeur de PAris et le routeur VPN, un réseau en `92.56.78.0/24`  
Entre celui de Paris et Lille, un réseau en `92.12.34.0/24`
On va choisir un réseau publique (`203.0.113.0/24`) pour le switch où les gens se connecteront au VPN   
<br/>
## Plan Paris  
Lan : `10.0.0.0/22` (1022 adresse, de `10.0.0.1` à `10.0.3.254`, ça laisse de la marge)  
DMZ et R&D : `192.168.0.0` (252 adresses, même réseau dans debatiments séparés relié en fibre)  
Wifi : `10.110.0.0/22` (1022 adresses, de `10.110.0.1` à `10.110.3.254`)  
VPN : `203.0.113.0/24` (254 adresses)  
<br/>
## Plan Lille  
Lan : `10.1.0.0/22` (1022 adresses, de `10.1.0.1` à `10.1.3.254`)  
Wifi : `10.111.0.0` (1022 adresse, de `10.111.0.1` à `10.111.3.254`)


## Packet Tacer  

<img width="1871" height="703" alt="image" src="https://github.com/user-attachments/assets/d95e433b-b738-4846-b0ca-a3d4398b900b" />



