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
subgraph Connection en ethernet
id1 e1@--- id2[PC]
id1 e1@--- id3[Portable]
id1 e1@--- id4[Xbox]
end
subgraph Connection en wifi
id1 ~~~ id5(Smartphone)
id1 ~~~ id6(Tablette)
end
e1@{ curve: linear }

```

## Diagramme logique de mon réseaux

```mermaid
flowchart TB
id1((Internet)) <---> id2([Routeur
Seveur DHCP])


id2 <---> id22>Switch
192.168.1.254]
id22 <--->id21[\Firewall\]
id22 <--->id23[\Firewall\]

id21 <---> id3[Windows 11
192.168.1.35]
id23 <---> id9[Ubuntu
192.168.1.32]
id3 <---> id20{Connection NAT}
subgraph Virtualisation
id20 <---> id4[Win-10-vm]
id20 <---> id5[Win-11-vm]
id20 <---> id6[Ubuntu-vm]
id20 <---> id7[Debian-one]
id20 <---> id8[Debian--two]
end
id2 <-.-> id10(Android)
id2 <-.-> id11(linux)
```
