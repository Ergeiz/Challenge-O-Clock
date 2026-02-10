
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

