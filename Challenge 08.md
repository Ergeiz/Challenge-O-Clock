# Énoncé
> ⌨️ Challenge
>
> **Avec l’outil de votre choix (draw.io, par exemple) tentez de réaliser un diagramme réseau de votre réseau domestique.**  
>
> Essayez de n’oublier aucun équipement connecté au WiFi ou en filaire à votre box !
>
> **Bonus:** _vous pouvez aussi commencer à votre renseigner sur les adresses IP et le calcul de sous-réseaux. Il y a plein de vidéos qui traitent de ce sujet sur YouTube_ 😉

## Diagramme physique de mon réseau

```mermaid
flowchart TB
id10(((Exterieur))) ---|- Fibre -| id1([Box Internet
Router
Switch
])
subgraph "Ethernet - RJ45"
id1 e1@--- id2[PC]
id1 e1@--- id3[PC Portable]
id1 e1@--- id4[Xbox]
end
subgraph "Wi-Fi 2,4 GHrz, 802.11n"
id1 ~~~ id5(Smartphone)
id1 ~~~ id6(Tablette)
end
e1@{ curve: linear }

```

## Diagramme logique de mon réseaux

```mermaid
flowchart TB

id1((Internet)) <---> id24[\Firewall\]
id24 <---> id2([Routeur
192.168.1.254])
id2 <---> id35@{ shape: procs, label: "Serveur DHCP"}

id35 <---> id22>Switch]
id35 <--->  id25>WI-FI 2,4GHrz WPA2 - AES
]
id22 <---> id21[\Firewall\]
id22 <---> id23[\Firewall\]
id22 <---> id30[Xbox
192.168.1.10]

id21 <---> id3[Windows 11
192.168.1.35]
id23 <---> id9[Ubuntu
192.168.1.32]
id3 <---> id20{ NAT
10.0.2.15 }

subgraph "`**Machines   virtuelles**`"
direction LR
id20 <---> id4[Win-10-vm]
id20 <---> id5[Win-11-vm]
id20 <---> id6[Ubuntu-vm]
id20 <---> id7[Debian-one]
id20 <---> id8[Debian--two]
end
id25 <-.-> id10(Android
192.168.1.29)
id25 <-.-> id11(linux
192.168.1.16)
```
