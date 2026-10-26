# Studio Octet : le système informatique

Dépôt de l'équipe informatique de Studio Octet, studio indépendant de jeux vidéo (entreprise fictive).
Projet de démarrage TSSR / AIS, Diginamic Formation.

> Aucun mot de passe dans ce dépôt. Tous les secrets sont dans Bitwarden.

## L'équipe

| Rôle | Nom | S1 | S2 | S3 |
|---|---|---|---|---|
| AIS, chef d'équipe | ... | Chef d'équipe | Chef d'équipe | Chef d'équipe |
| TSSR A | ... | Proxmox & Réseau | Windows | Linux |
| TSSR B | ... | Windows | Linux | Proxmox & Réseau |
| TSSR C | ... | Linux | Proxmox & Réseau | Windows |

## Schéma du réseau

Déposez votre schéma dans `preuves/schema.png`, puis remplacez cette ligne par :
`![Schéma du réseau](preuves/schema.png)`

## Plan d'adressage

Réseau du studio : `192.168.10.0/24` · Domaine : `studio-octet.lan`

| Équipement | Nom | Adresse IP | Hébergé sur |
|---|---|---|---|
| Routeur (passerelle) | — | | Physique |
| Proxmox VE n°1 | pve1 | | Physique |
| Proxmox VE n°2 | pve2 | | Physique |
| Proxmox Backup Server | pbs | | Physique |
| Windows Server (AD, DNS, DHCP) | SRV-AD01 | | PVE1 |
| Conteneur Uptime Kuma | kuma | | PVE1 |
| Conteneur GLPI | glpi | | PVE2 |
| Conteneur intranet | intranet | | PVE2 |
| Poste Windows 11 | PC-TEST01 | DHCP | PVE2 |
| Plage DHCP | — | de ... à ... | SRV-AD01 |

## Accès

Les mots de passe sont dans Bitwarden, jamais ici.

| Service | Adresse |
|---|---|
| Proxmox PVE1 | https://...:8006 |
| Proxmox PVE2 | https://...:8006 |
| Proxmox Backup Server | https://...:8007 |
| Uptime Kuma | http://...:3001 |
| GLPI | http://glpi.studio-octet.lan |
| Intranet | http://intranet.studio-octet.lan |

## Organisation du dépôt

| Dossier | Contenu |
|---|---|
| `fiches/` | Une fiche par service (modèle : `fiches/_modele-fiche-service.md`) |
| `journal/` | Un fichier par jour (modèle : `journal/_modele-journal.md`) |
| `preuves/` | Les captures d'écran des achievements |
| `salaries.csv` | Les 12 salariés à créer dans l'Active Directory |

## Ouvrir une issue

Cliquez sur **Issues > New issue** et choisissez un formulaire :

- **Achievement** : déclarer un achievement débloqué, avec sa preuve ;
- **Carte Chaos** : traiter une panne simulée ;
- **Question au formateur** : quand vous êtes bloqués depuis plus de 45 minutes.
