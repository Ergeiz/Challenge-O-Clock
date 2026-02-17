# Énoncé

<details>
<summary> <h2>Consulting Cloud pour PME</h2> </summary>
<blockquote>
<hr />
<h2>Contexte</h2>

 Vous êtes consultant chez TechConseil. Votre client MediCare+ (PME de services de santé) veut moderniser son IT. L’infrastructure est 100% on‑premises et l’équipe est peu à l’aise avec le cloud.

 Votre mission : proposer une stratégie cloud simple, cohérente et réaliste.
 Le client en bref

<ul>
<li>50 employés, siège à Lyon, agences à Marseille et Paris</li>
<li>Application métier interne (PHP/MySQL), critique pour l’activité</li>
<li>Site web vitrine WordPress</li>
<li>Données sensibles mais pas de dossiers médicaux complets</li>
<li>Un administrateur système à mi‑temps</li>
</ul>

<hr />
<h2>Infrastructure actuelle (résumé)</h2>

<ul>
<li>Active Directory + DNS/DHCP sur un serveur Windows</li>
<li>Application métier + base MySQL + fichiers sur un serveur Windows</li>
<li>Site web sur un petit serveur Linux</li>
<li>NAS + sauvegardes manuelles</li>
<li>VPN inter‑sites</li>
</ul>

Coût annuel estimé : ~46 000 €

<hr />
<h2>Problèmes constatés</h2>

<ul>
<li>Coûts élevés et matériel à renouveler</li>
<li>Disponibilité limitée, sauvegardes manuelles</li>
<li>Accès distant difficile pour le télétravail</li>
<li>Montée en charge compliquée</li>
<li>RGPD pas assez cadré</li>
</ul>

<hr />
<h2>Objectifs du client</h2>

<ul>
<li>Réduire les coûts et la maintenance</li>
<li>Améliorer disponibilité et collaboration</li>
<li>Sécuriser et cadrer la conformité RGPD</li>
<li>Préparer la croissance</li>
</ul>

<hr />
<h2>Votre mission (livrable attendu)</h2>

Vous remettez un document de recommandation. Pas besoin d’un pavé : 2 à 3 pages suffisent si c’est clair.

Le document contient :

<h3><b>1. Architecture cible (le cœur du travail)</b></h3>

Pour chaque composant, proposez une cible simple : On‑prem, IaaS, PaaS ou SaaS, avec le provider et la justification.

<table>
<thead>
<tr>
<th align="center"><b>Composant</b></th>
<th align="center"><b>Proposition</b></th>
<th align="center"><b>Modèle</b></th>
<th align="center"><b>Provider</b></th>
<th align="center"><b>Justification courte</b></th>
</tr>
</thead>
<tbody><tr>
<td align="center">Identités</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Messagerie + bureautique</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Fichiers partagés</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">App métier</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Base de données</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Sauvegardes</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Site web</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
</tbody></table>
			

Ajoutez un schéma simple (même à la main) : utilisateurs → services principaux → données.

<h3><b>2. Choix du provider</b></h3>

Comparez 2 ou 3 providers (Azure, AWS, OVHcloud, etc.).

<table>
<thead>
<tr>
<th align="center"><b>Critère</b></th>
<th align="center"><b>Azure</b></th>
<th align="center"><b>AWS</b></th>
<th align="center"><b>OVHcloud</b></th>
</tr>
</thead>
<tbody><tr>
<td align="center">Localisation France</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Services managés (PaaS)</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Coût estimé</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
<tr>
<td align="center">Support / simplicité</td>
<td align="center"></td>
<td align="center"></td>
<td align="center"></td>
</tr>
</tbody></table>
	

Concluez en 4 ou 5 lignes : le provider retenu et pourquoi.

<h3>3. Estimation budgétaire (ordre de grandeur)</h3>

Donnez une estimation mensuelle globale (pas besoin d’être exact) et expliquez vos hypothèses.
<h3>4. Points d’attention</h3>

Listez 3 à 5 risques majeurs et comment vous les réduisez (ex : migration, sécurité, dépendance fournisseur).

<hr />
<h2>Conseils</h2>

<ul>
<li>Restez simples et cohérents.</li>
<li>Mieux vaut une solution sobre et justifiée qu’un catalogue de services.</li>
<li>Si vous manquez de temps, priorisez l’architecture et le choix du provider.</li>
</ul>

<hr />
<h2>Rendu</h2>

Un document unique par groupe. Le format est libre (PDF, Word, Google Docs).

Bonne chance, et posez des questions si besoin.
</blockquote>

</details>

# Réponse

### Pour l'architecture cible

| Composant | Proposition | Modèle | Provider | Justification courte |
|---|---|---|---|---|
| Identités | Entra ID + synchro Azure AD Connect + MFA/SSO| Hybrid | Azure | Centralise l'identité, mfa, sso. Garde la syncro locale. |
| Messagerie + bureautique | Microsoft 365 | SaaS | Azure | Standard pour une PME, maintenance réduite, possibilité de collaboration, sécurité intégré |
| Fichiers partagés | Sharepoint/ OneDrive (Microsoft 365) | SaaS | Azure | Partage et accès distant simple |
| App métier | App Service ou VM linux | PaaS ou IaaS | Azure | PaaS pour moins d'admin et montée en charge simple, IaaS si application non migrable |
| Base de données | Azure MySQL Flexible Server  | PaaS | Azure | Service managé, sauvegarde, HA possible |
| Sauvegardes | Azure Backup + Recovery Services Vault + politiques de rétention | PaaS | Azure | Remplace sauvegardes manuelles, restauration fiable, RGPD |
| Site web | WordPress managé (App Service + MySQL) | PaaS | Azure | Maintenance simplifié, disponibilité |

### Pour le choix du Privider

| Critère | Azure | AWS | GCP | OVHcloud | Scaleway |
|---|---|---|---| --- | --- |
| Localisation France | Oui (choix France central ou Sud) | Oui (Paris) | Oui (Paris) | Oui | Oui |
| Services managés (PaaS) | Très complet, intégration Nicrosoft 365 | Très complet, plus complexe | Complet, adapté pour du data analitycs ou dev | PaaS plus limité, adapté pour du IaaS | Plutôt adapté pour du IaaS |
| Coût estimé | Moyen, optimisable avec les bundle Microsoft | Élevé à configuration équivalente | Moyen à élevé selon les services | moins cher en IaaS | Compétitif sur VM |
| Support / simplicité | Bonne intégration pour les PME utilisant les produits Microsofts | Plus complexe | Inteface claire mais utilisations plus contextuelles | Ádministration simple mais plus de choses à gérer pour la PME | Simple mais nécéssite plus d'administration |

### En conclusion

L'entreprise utilise déja des outils Windows, cela facilite donc la migration vers Azure.
Les services PaaS proposés permettent de réduire la charge d’exploitation et d’améliorer la disponibilité des applications.
La présence de datacenters en France répond aussi aux contraintes RGPD de localisation des données.
Cette solution est la mieux adapté, elle offre une simplicité d’administration, de nombreuses fonctionnalités et des possibiltés d'évolution dans le futur.

### Estimation budgetaire

|  Service | Estimation au mois (approximatif) |
| --- | --- |
| Microsoft 365 business premium pour 50 personnes | 1000€ |
| Applications métier (App Service ou vm) | 150€ - 250€ |
| MySQL en PaaS | 120€ - 180€ |
| Azure Backup / stockage | 80€ - 120€ |
| Site Wordpress | 20€ - 50€ |
| Total | environ 1400€ - 1600€ par mois |

> [!Note]
> Les couts peuvent varier selon le nombre d’utilisateurs, les performances nécessaires des ressources cloud, les volumes de stockage et de sauvegarde, les besoins de haute disponibilité et de trafic réseau

### Risques majeures

| Risques | Actions envisageables |
| --- | --- |
| Dépendance | Privilégier les technologies standardisées, documenter l'architecture, sauvegarde exportable hors plateforme |
| Migration (incompatibilité technique ou interruption de service) | audit technique avant migration, environnement de test, migration par lot |
| Sécurité (mauvais controle des accés, fuite de donnees) | MFA, audit de sécurité régulier |
| Budget (ressource mal dimensionnées ou mal utilisées ) | Dimensinnement initial prudent, revue mensuelle des ressources |
| Cloud indisponible | Sauvegarde régilière, réplication multi-zone |
