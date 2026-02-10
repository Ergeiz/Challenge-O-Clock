# Raccourcis

- [Challenge 2](#énoncé-e2)


# Énoncé E1
>
> ## Contexte
>
> Vous êtes responsable de l’informatique au sein d’un campus de formation professionnelle (en présentiel 😁).
>
> Le campus compte en permanence environ 500 personnes, entre les salariés (une quinzaine), les formateurs (freelances, formateurs occasionnels) et les apprenants (formation continue et alternance).
>
> La direction vous demande de moderniser l’infrastructure IT du campus pour accueillir de nouveaux services numériques : serveurs fichiers, NAS, firewall, VLAN et accès sécurisé Wi-Fi.
>
> Dans votre service, vous accueillez actuellement un alternant.
>
> ## Consignes
>
> Rédigez la fiche de cadrage du projet comprenant :
>
>   - Objectifs du projet
>   - Périmètre et exclusions
>   - Parties prenantes (interne / externe)
>   - Livrables principaux
>   - Contraintes Qualité / Coût / Délai
>
> ## Notes
>
>   - Vous pouvez rédiger votre document avec l’outil de votre choix (Google Doc, fichier Markdown…)
>   - Gardez bien le fichier : il servira pour la suite !
>   - Prenez le temps de chercher de la documentation sur le sujet
>   - On ne demande pas d’être exhaustif, chaque partie peut ne contenir que quelques points
>
# Fiche de cadrage

## Objectifs du projet
- Moderniser l’infrastructure informatique du campus afin de supporter les nouveaux usages numériques.
- Mettre en place une architecture réseau sécurisée intégrant :
    - un système de stockage centralisé (serveurs fichiers / NAS),
    - un firewall de nouvelle génération,
    - une segmentation réseau par VLAN,
    - un accès Wi-Fi sécurisé pour les apprenants, formateurs et personnel administratif.
- Améliorer la disponibilité, la sécurité et la performance des services informatiques.
- Préparer l’infrastructure à l’augmentation future du nombre d’utilisateurs et de services numériques.

## Périmètre du projet
### Inclus
- Audit de l’infrastructure existante.
- Conception de l’architecture réseau cible.
- Acquisition et déploiement :
  - firewall,
  - NAS / serveurs fichiers,
  - équipements réseau compatibles VLAN,
  - bornes Wi-Fi sécurisées.
- Configuration des VLAN (administration, pédagogie, invités, infrastructure).
- Mise en place des mécanismes d’authentification et de sécurité Wi-Fi.
- Documentation technique et transfert de compétences.
### Exclus
- Développement applicatif spécifique.
- Renouvellement du parc informatique utilisateur.
- Gestion du support utilisateurs après mise en production (hors phase projet).

## Parties prenantes
### Internes
- Direction du campus (sponsor du projet)
- Responsable informatique (chef de projet)
- Alternant IT (support technique projet)
- Personnel administratif
- Formateurs
- Apprenants
### Externes
- Fournisseurs matériels (réseau, NAS, firewall)
- Prestataires d’intégration / infogérance (si nécessaire)
- Opérateur Internet
- Mainteneurs des équipements

## Livrables principaux
- Étude d’existant et analyse des besoins.
- Dossier d’architecture technique cible.
- Plan d’adressage IP et plan VLAN.
- Infrastructure réseau déployée et opérationnelle.
- Documentation d’exploitation (procédures, schémas réseau).
- Rapport de recette et validation de mise en production.

## Contraintes Qualité / Coût / Délai
### Qualité
- Haute disponibilité des services critiques.
- Conformité aux bonnes pratiques de sécurité réseau.
- Documentation complète et maintenable.
- Performance réseau adaptée à ~500 utilisateurs simultanés.

### Coût
- Respect du budget validé par la direction.
- Optimisation des coûts via mutualisation des équipements et solutions adaptées.

### Délai
- Déploiement progressif sans interruption majeure de service.
- Mise en production complète dans le délai défini par la direction (ex. 4 à 6 mois).

## Méthode de gestion recommandée *(correction)*
Pour mener a bien ce projet, plusieurs méthodologies peuvent être combinées:

- **Cycle en V :** cette méthode séquentielle structure le projet en phases distincte (analyse des besoins, conception, réalisation, tests, validation). Elle permet de garantir que chaque étape est validée avant de passer à la suivante, ce qui est particulièrement adapté aux projets d'infrastructure où la sécurité et la fiabilité sont critiques.
- **Méthode Agile :** l'utilisation de sprints courts permet d'apporter de la flexibilité au projet. Des ajustements peuvent être réalisés rapidement en fonction des retours terrain ou des contraintes techniques découverte en cours de route
- **Approche DevOps :** cette approche favorise l'automatisation de la configuration des serveurs, du déploiment des services et des tests, Elle permet de gagner du temps, de réduire les erreurs humaines et d'assurer une mise en production plus rapide.

# Agile

> À faire également Lire le Manifeste pour le développement Agile de logiciels: https://agilemanifesto.org/iso/fr/manifesto.html
> 
> Commenter le Manifeste (questions, points positifs, critiques…) dans un fichier (libre choix de l’outil).

## WBS

# Énoncé E2

> ## Contexte
>
> Vous êtes responsable de l'informatique au sein d'un campus de formation professionnelle (en présentiel 😁).
>
> Le campus compte en permanence environ 500 personnes, entre les salariés (une quinzaine), les formateurs (freelances, formateurs occasionnels) et les apprenants (formation continue et alternance).
>
> La direction vous demande de moderniser l'infrastructure IT du campus pour accueillir de nouveaux services numériques : serveurs fichiers, NAS, firewall, VLAN et accès sécurisé Wi-Fi.
>
> Dans votre service, vous accueillez actuellement un alternant.
> ## Consignes
>
> Hier vous avez créé la note de cadrage du projet.
>
> Aujourd'hui on vous demande de créer un WBS avec plusieurs niveaux de tâches :
>
> - Niveau 1 : grands lots (serveur, NAS, firewall, réseau)
> - Niveau 2-3 : tâches et sous-tâches
>
> ## Notes
>
> - Vous pouvez utiliser les outils de votre choix pour la représentation graphique
> - Gardez bien le fichier : il servira pour la suite !
> - Prenez le temps de chercher de la documentation sur le sujet
>




```mermaid

---
title: Modernisation de l'infrastructure IT du campus
---
flowchart TD

  


  %% -- Niveau 1 (grands lots) --
  %% S["1.1 Serveur"]
  %% N["1.2 NAS / Stockage"]
  %% F["1.3 Firewall / Sécurité périmétrique"]
  %% R["1.4 Réseau (VLAN + Wi-Fi sécurisé)"]

  %% ### Partie Serveurs ###

subgraph sub1 [ ]
direction TB
  
  subgraph "1 - Serveurs"
  direction TB
  subgraph "1.1 Cadrage & préparation"
  direction RL
  S11["1.1.1 Définition des besoins (comptes, partages, quotas)"]
  S12["1.1.2 Choix de l'OS et des rôles (AD/LDAP, fichiers, sauvegardes)"]
  S13["1.1.3 Dimensionnement CPU,RAM et stockage"]
  end

  subgraph "1.2 Mise en place"
  direction RL
  S21["1.2.1 Installation OS + durcissement (SSH, MAJ, pare-feu)"]
  S22["1.2.2 Services fichiers (SMB/NFS) + droits"]
  S23["1.2.3 Supervision & journalisation (logs, alertes)"]
  end

  subgraph "1.3 Validation & mise en prod"
direction RL
  S31["1.3.1 Tests accès (apprenants/formateurs/salariés)"]
  S32["1.3.2 Plan de bascule + rollback"]
  S33["1.3.3 Documentation + transfert (alternant/équipe)"]
  end
  end

  %% ### Partie NAS ###
  subgraph "Nas / Stockage"
  direction TB
  subgraph "2.1 Cadrage & conception"
  direction RL
  N11["2.1.1 Choix des technos (RAID, ZFS/Btrfs, iSCSI/SMB/NFS)"]
  N12["2.1.2 Définition de la politique de sauvegarde (3-2-1, rétention)"]
  N13["2.1.3 Plan de la gestion des droits (partages, groupes, quotas)"]
  end

  subgraph "2.2 Déploiement"
  direction RL
  N21["2.2.1 Installation du NAS & configuration du stockage"]
  N22["2.2.2 Création des partages & ACL"]
  N23["2.2.3 Sauvegardes (jobs, tests des restauration --> très important)"]
  end

  subgraph "2.3 Exploitation"
  direction RL
  N31["2.3.1 Monitoring (disques, SMART, capacité)"]
  N32["2.3.2 Mises à jour & maintenance"]
  N33["2.3.3 Procédures incident / PRA (si prévu)"]
  end
  end

  %% Partie Firewall ###
  subgraph Firewall
  direction TB
  subgraph "3.1 Architecture & règles"
 direction RL
  F11["3.1.1 Cartographie des réseaux"]
  F12["3.1.2 Politique de filtrage"]
  F13["3.1.3 Accès distant sécurisé via VPN"]
  end

  subgraph "3.2 Implémentation"
  direction RL
  F21["3.2.1 Installation appliance/VM"]
  F22["3.2.2 NAT / règles / objets / aliases"]
  F23["3.2.3 Services sécurité, DNS filtrant si prévu"]
  end

  subgraph "3.3 Tests & exploitation"
  direction RL
  F31["3.3.1 Tests règles et isolement VLAN"]
  F32["3.3.2 logs et alert"]
  F33["3.3.3 Documentation (règles, VPN, procédures)"]
  end
  end

  %% ### Partie Réseaux ###
  subgraph "Réseaux"
  direction TB
  subgraph "4.1 Conception réseau"
  direction RL
  R11["4.1.1 Plan d’adressage IP et sous-réseaux"]
  R12["4.1.2 attribution VLAN (salariés, formateurs, apprenants, invités, admin)"]
  R13["4.1.3 Matériel & topologie (switchs, AP, liens)"]
  end

  subgraph "4.2 VLAN & switch"
direction RL
  R21["4.2.1 Configuration trunks/access"]
  R22["4.2.2 Routage entre VLAN (via firewall/L3)"]
  R23["4.2.3 Services réseau (DHCP par VLAN, DNS, NTP)"]
  end

  subgraph "4.3 Wi-Fi sécurisé"
  direction RL
  R31["4.3.1 SSID par profils (interne, apprenants, invités)"]
  R32["4.3.2 Sécurité (WPA2/3-Enterprise)"]
  R33["4.3.3 Portail invité / isolation clients (si prévu)"]
  end

  subgraph "4.4 Tests & recette"
  direction RL
  R41["4.4.1 Tests couverture Wi-Fi et itinérent"]
  R42["4.4.2 Tests de segmentation des VLAN"]
  R43[".4.4.3 Recette et documentation"]
end
  end
  end
```
