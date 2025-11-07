
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

# Materiel

Nous devront faire le réseau avec le matériel prevu :
| Matériel | Total | Image
|:---:|:---:|:--:|
| Routeurs Cisco 2901 | 2 | ![CISCO2901_lg](https://github.com/user-attachments/assets/cad81a5e-c9cb-47a6-b745-4a910147f85c) |
| Routers Cisco 1941 | 1 |  ![cisco-router-1900-series-cisco-1941-k9-sale-repair-rental-500x500-600x600-2882285535](https://github.com/user-attachments/assets/3a3f2e5e-5e70-45a4-b808-49bb54b96d7d) |
| carte routeur HWIC-1GE-SFP | 5 | <img width="636" height="240" alt="HWIC-1GE-SFP-2472865841" src="https://github.com/user-attachments/assets/a5327111-6a52-4453-8bf9-e14aeffcffe0" /> |
| Module routeur et switch SFP GLC-LH-SMD | 10 | ![startechcom-gigabit-fiber-sfp-transceiver-module-cisco-glc-lh-smd-compatible-sm-mm-lc-10km-550m-34046655](https://github.com/user-attachments/assets/c2a755c5-ff2c-46a2-87c0-3565e61f5d22) |
| Cartes routeur HWIC-2T | 2 | ![HWIC-2T-1-800x800-1010479136](https://github.com/user-attachments/assets/f1260246-a883-47b5-a14b-8c20d22b3b30) |
| Switchs Cisco 3650-24PS | 4 | ![OIP-1178791405](https://github.com/user-attachments/assets/6a6ee548-04cd-4d16-ae41-ac9c4f77f579) |
| Switchs Cisco 2960-24TT | 3 | ![switches-catalyst-2960-24tt-l-switch-3971075008](https://github.com/user-attachments/assets/67b4fe91-f2e0-4254-9407-a6e1d1655f6d) |
| Alimentation AC-POWER-SUPPLY pour switch Cisco 3650-24PS | 4 | ![s-l1600-4099920913](https://github.com/user-attachments/assets/e2bb4d3d-6055-4ec3-a2c4-286f4a9e9d7e) |

Autres équipements : 
- 4 serveurs
- 3 copieurs

## Packet Tacer - Répartition du matériel

<img width="1856" height="712" alt="image" src="https://github.com/user-attachments/assets/1095fb26-494e-4519-aaf7-693b6de413a1" />

Nous avons reparti le materiel de cette façon:  
- les switchs Cisco 3650-24PS pour les réseaux Lan, Dmz et R&D  
- les switchs Cisco 2960-24TT pour les réseaux WiFi et le vpn  
- Un routeur Cisco 2901 pour le réseau de Paris et un pour le réseau de Lille  
- Le routeur Cisco 1941 pour le VPN  


Pour les cartes et modules:  
- Dans le Switch R&D nous mettons un AC-POWER-SUPPLY et un SFP GLC-LH-SMD  
- Dans le Switch Serveurs un AC-POWER-SUPPLY et 2 SFP GLC-LH-SMD  
- Dans le SwitchLanParis un AC-POWER-SUPPLY et un SFP GLC-LH-SMD  
- Dans le SwitchLanLille un AC-POWER-SUPPLY et un SFP GLC-LH-SMD  
- Dans le routeur RouterParis 3 HWIC-1GE-SFP avec 3 SFP GLC-LH-SMD, et un HWIC-2T  
- Dans le RouterLille un HWIC-1GE-SFP avec un GLC-LH-SMD  
- Dans le routeur VPN un HWIC-1GE-SFP avec un SFP GLC-LH-SMD, et un HWIC-2T  
  
## Packet Tracer - configuration


<img width="1861" height="712" alt="image" src="https://github.com/user-attachments/assets/8ee9fc70-e7fd-4ef7-b337-eeb7e53f3325" />


nous configurons tous les switch, par exemple avec celui du réseau R&D
```
switch> enable
switch# conf t
switch (config)# interface vlan1
switch (config-if)# ip address 192.168.0.252 255.255.255.0
switch (config-if)# no shutdown
switch (config-if)# exit
switch (config)# hostname r&d
r&d (config)# enable secret wsxwsx
r&d (config)# end
r&d# wr m

```
nous configurons ensuite le routeur de Paris, il doit être connecté à 4 sous-reseau, par exemple pour le gateway de la DMZ
```
router> enable
router# conf t
router(config)# interface gigabitEthernet 0/0/0
router (config-if)# ip address 192.168.0.1 255.255.255.0
router (config-if)# no shutdown
router (config-if)# end
```


on en profite pour changer le hostname et ajouter un mot de passe  
on fait pareil avec les autres routeurs  
ensuite pour les routage, sur le serveur de Paris, on fait une route statique ciblant le réseau 203.0.112.0 vers le serveur VPN et une route par défaut vers le serveur de Lille :

```
ServerParis> enable
ServerParis# conf t
ServerParis (config)# ip route 203.0.113.0 255.255.255.0 92.56.78.2
ServerParis (config)# ip route 0.0.0.0 0.0.0.0 92.12.34.2
```

<img width="677" height="218" alt="image" src="https://github.com/user-attachments/assets/b8b2a57f-d458-4dad-b9f9-b64c032343f0" />


Ce qui voudra sortir tout en ne ciblant pas le réseau VPN ira vers le serveur de Lille
on fait une route par défaut sur le server de Lille en direction du server de Paris, de même avec le serveur vpn en direction du server de Paris

Maintenant, certaines machines ont une addresse ip statique, mais d'autre attendent serveur dhcp leur en attribue une, on peut le faire avec un routeur.

Au niveau du routeur, uil faudra définir un pool pour chaque sous réseau
Si on veut configurer un pool pour le lan de Paris :
```
RouterParis (config)# ip dhcp pool LAN1
RouterParis (dhcp-config)# network 10.0.0.11 255.255.252.0
RouterParis (dhcp-config)# default-router 10.0.0.1
RouterParis (dhcp-config)# dns-server 8.8.8.8
RouterParis (dhcp-config)# exit
RouterParis (config)# ip dhcp excluded-address 10.0.0.1 10.0.0.10
RouterParis (config)# end
```

 <img width="470" height="522" alt="image" src="https://github.com/user-attachments/assets/78194884-3a26-4d3f-ba6a-8012db1a34d9" />

<img width="905" height="350" alt="image" src="https://github.com/user-attachments/assets/627a3aea-45d5-49f0-abe2-c5a367a25f66" />

Si on tente un ping sur un pc du lan de Lille

<img width="1833" height="505" alt="image" src="https://github.com/user-attachments/assets/fce32815-c61d-4491-9c75-a049357c3cfd" />

ou sur un ordi du R&D

<img width="1125" height="652" alt="image" src="https://github.com/user-attachments/assets/2acca112-3b39-4723-8dd6-ed1afa4ba716" />

Le DHCP est plutôt fonctionnel

La suite de l'exercice étant de remplacer les switchs WiFi par des relay et d'ajouter un serveur DHCP dans la DMZ et le faire faonctionner sur les deux sous réseau lan et DMZ


<img width="1843" height="709" alt="image" src="https://github.com/user-attachments/assets/b54e6850-4ffd-4683-b659-94cc97576281" />

J'ai pas beaucoup d'option de configuration sur les relays WiFi, j'imagine que ça se joue au niveau du router  

Du coup occupons nous du server DHCP.
Déjà j'efface les pool configuré sur le router
```
RouterParis (config)# no ip dhcp pool LAN1
```
Ainsi que les plages d'address exclues du DHCP

```
RouterParis (config)# no ip dhcp excluded-address 10.0.0.1 10.0.0.10
```
On fait ca pour les 3 sous-réseau, normalement il ne reste plus rien dans la config

Maintenant dans le serveur DHCP on va faire un pool pour chaque sous-réseau

<img width="980" height="453" alt="image" src="https://github.com/user-attachments/assets/a3e2f393-77d5-453d-9a83-ab939a609334" />

Ensuite il faut indiquer au routeur de relayer les trames de diffusion dhcp vers le server dhcp, pour cela nous retournons dans la CLI
Dans l'interface lié au réseau du DHCP, on va rajouter une commande
 ```
RouterParis (config)# interface gigabitEthernet 0/0/0
RouterParis (config-if)# ip helper-address 192.168.0.254
```
On met bien l'ip du serveur DHCP, on sauvegarde tout ça, puis on jette un oeil sur les machines en les passant en statique pui DHCP

<img width="1432" height="363" alt="image" src="https://github.com/user-attachments/assets/4d94c789-9d3c-49bc-b5f5-a2b611c7373d" />


<img width="1470" height="321" alt="image" src="https://github.com/user-attachments/assets/ca63f056-19c4-4cc5-a822-abcd6b27b8d1" />

ca m'a l'air fonctionnel

<img width="609" height="518" alt="image" src="https://github.com/user-attachments/assets/8f3a22e3-0271-440b-9995-63334dc2d800" />
sur le router aucune trace de configuration DHCP donc c'est bien notre serveur DHCP qui traite les qttribue des addresse IP sur les autres sous réseau

Pour la parie de Lille je garde la config DHCP du RouterLille

<img width="483" height="538" alt="image" src="https://github.com/user-attachments/assets/01e25ffa-2c32-40fa-8bea-1bcc3ab8e85c" />












