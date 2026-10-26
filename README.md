# Studio Octet : le système informatique

Dépôt de l'équipe informatique de Studio Octet, studio indépendant de jeux vidéo (entreprise fictive).
Projet de démarrage TSSR / AIS, Diginamic Formation.

> Aucun mot de passe dans ce dépôt. Tous les secrets sont dans Bitwarden.

## Organisation du dépôt

| Dossier | Contenu |
|---|---|
| `documentation/` | Les documents du projet en PDF : brief client, guide du projet, architecture et matériel, fiches missions, achievements, modèles |
| `données/` | Les données du projet, dont `salaries.csv` : les 12 salariés à créer dans l'Active Directory |
| `fiches/` | Une fiche par service (modèle : `fiches/_modele-fiche-service.md`) |
| `journal/` | Un fichier par jour (modèle : `journal/_modele-journal.md`) |
| `preuves/` | Les captures d'écran des achievements |

## Comment utiliser ce dépôt

Ce dépôt est **le dossier de travail de l'équipe** : tout ce que vous faites pendant les 3 semaines doit s'y retrouver. Il sert aussi de base à votre évaluation (fiches et preuves comptent pour 20 % de la note). Souvenez-vous : *ce qui n'est pas prouvé n'existe pas, ce qui n'est pas documenté sera oublié.*

Tout se fait **depuis le site GitHub**, sans ligne de commande : **Add file > Create new file** pour écrire un fichier, **Add file > Upload files** pour déposer une capture, **Issues > New issue** pour ouvrir une issue.

### Le premier jour

1. Lisez les documents de `documentation/`, en commençant par le brief client et le guide du projet.
2. Remplissez le tableau **L'équipe** ci-dessous : qui est l'AIS, qui sont les TSSR A, B et C.
3. Créez le tableau **Projects** avec 3 colonnes : À faire, En cours, Fait.

### Chaque jour

- **9 h 00** : point du matin (ce que je fais aujourd'hui, ce qui me bloque). Mettez à jour le tableau Projects.
- **Pendant la journée** : à chaque service installé, créez ou complétez sa fiche dans `fiches/` en copiant le modèle. Elle doit permettre à un débutant de vérifier, réinstaller et dépanner le service. Faites-la relire par un coéquipier et complétez le tableau de `fiches/README.md`.
- **À chaque achievement débloqué** : déposez la capture dans `preuves/` (en suivant le nommage indiqué dans `preuves/README.md`), puis ouvrez une issue **Achievement**. L'AIS vérifie la preuve avant de la fermer.
- **16 h 45** : écrivez le journal du jour dans `journal/AAAA-MM-JJ.md` en copiant le modèle.

### Au fil du projet

- Tenez à jour le **schéma du réseau**, le **plan d'adressage** et le tableau des **accès** ci-dessous (sans aucun mot de passe).
- Quand une **Carte Chaos** tombe, ouvrez une issue **Carte Chaos** tout de suite, notez l'heure, et documentez la cause et la réparation.
- Bloqué depuis 20 min : demandez à l'équipe. Depuis 45 min : demandez à l'AIS. Toujours bloqué : ouvrez une issue **Question au formateur** et avancez sur autre chose en attendant.
- **Le vendredi**, appuyez-vous sur vos fiches pour la passation à la personne qui reprend votre domaine.

### À ne jamais faire

- Mettre un mot de passe dans un fichier, une issue ou une capture d'écran : vérifiez chaque capture avant de la déposer.
- Modifier ou supprimer les fichiers de `documentation/`, `données/` ou les modèles (`_modele-*.md`) : copiez-les plutôt.

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

## Ouvrir une issue

Cliquez sur **Issues > New issue** et choisissez un formulaire :

- **Achievement** : déclarer un achievement débloqué, avec sa preuve ;
- **Carte Chaos** : traiter une panne simulée ;
- **Question au formateur** : quand vous êtes bloqués depuis plus de 45 minutes.
