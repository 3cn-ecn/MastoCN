# MastoCN

Repository pour un projet de déploiement d'une instance Mastodon à Centrale Nantes.

## Pourquoi Mastodon ?

Mastodon se pose comme un concurrent direct à Twitter, se concentrant sur des messages courts et brefs. Il repose sur le protocole *ActivityPub*, lui permettant de communiquer avec d'autres logiciels du Fediverse, tels que *PixelFed* ou *PeerTube* par exemple. L'avantage de Mastodon est qu'il est totalement libre, aussi il est possible d'héberger soi-même sa propre instance Mastodon sur un serveur pour rester maître de ses données et indépendant des GAFAM.

L'avantage de Mastodon contrairement à d'autres logiciels libres concurrents est qu'il est plutôt stable, et propose une expérience de qualité égale voire supérieure aux réseaux sociaux privés traditionnels. Pour vous faire une idée, vous pouvez consulter l'instance la plus utilisée actuellement en France (à la date du 21/03/2023) : https://piaille.fr/. Des applications mobiles et bureau sont aussi disponibles pour tous les systèmes.

## Quelle utilité ?

Mastodon permettrait de diminuer notre dépendance à Facebook dans les échanges numériques de la vie étudiante de l'école. En pratique, il s'intègre dans un plan plus global de transition vers des outils plus respectueux de la vie privée et plus sûrs :

| Besoin | Outil actuel | Proposition de remplacement |
| --- | --- | --- |
| Organisation d'évènements | Facebook (Meta) | [Nantral Platform](https://nantral-platform.fr/) |
| Posts d'actus (annonce d'un évènement, questions, partages...) | Facebook (Meta) | [Mastodon](https://joinmastodon.org/) |
| Communication "officielle" sur l'actu de l'école | E-mail | [Mastodon](https://joinmastodon.org/) |
| Messagerie instantanée | Messenger (Meta) / Whatsapp (Meta) | Pas encore défini. *Pistes : Signal / Télégram (meilleure vie privée), Zoom (outil officiel actuel de l'école). Pas de solution en auto-hébergement viable pour l'instant.* |
| Rappels d'anniversaire | Facebook (Meta) | [Nantral Platform](https://nantral-platform.fr/) |
| Comm au format "story", vidéos courtes | Instagram (Meta) | [PixelFed](https://github.com/pixelfed/pixelfed) |
| Groupes à thèmes (CAC Annonces, Nantral GAG, 6-trouilles...) | Facebook (Meta) | Dans le cas d'une communication mono-directionnelle (type un club diffusant des annonces à ses membres), un compte de club sur Mastodon auquel s'abonnent les membres suffit. Dans le cas de groupes créés pour séparer les types de posts (CAC Annonces par exemple), les hastags peuvent être utilisés. |
| Vidéos longues (CNT-CNC, captations de spectacles, trailers...) | YouTube (Alphabet) | [PeerTube](https://www.peertube.fr/) |
| Espace de travail collaboratif | Google Drive (Alphabet) | [NextCloud](https://nextcloud.com/) (aka la "Box ECN") avec [Collabora](https://www.collaboraoffice.com/) ou [OnlyOffice](https://www.onlyoffice.com/fr/) |

Bien évidemment, ces transitions peuvent être faites indépendamment les unes des autres, en fonction des motivations des clubs et assos. À noter cependant que pour qu'elles soient effectives, elles nécessitent une volonté forte des BDX en charge, qui seuls ont la capacité d'effectuer une transition d'un service vers un autre.

À noter aussi que chaque service alternatif proposé repose sur l'auto-hébergement, ce qui peut entraîner des coûts non-négligeables (pour le BDE ou l'école suivant l'organisation hébergeante).

## Comparaison avec Facebook

### Avantages

* Pas de censure : la censure automatique de Facebook est devenue plus agressive récemment, notamment par le fait qu'un post fait par un club qui contient un lien vers un autre site est systématiquement supprimé
* Plus simple à utiliser : Mastodon reprend le principe d'un compte basique et universel, peut importe que ce soit pour une personne ou un club, sur le modèle d'Instagram. Donc pas de pages avec des paramètres cachés à gérer ou de prises de tête pour les passations ou changement de nom.
* Pas de pubs, pas de tracking inter-sites, pas de revente de données : toutes les données sont directement gérées localement
* Formats plus court : les posts sont limités à un certain nombre de caractères (sur le modèle de Twitter), ce qui incite à faire des messages courts qui retiennent l'attention (et si besoin on peut toujours faire plusieurs posts qui s'enchaînent).
* Ouvert : il est possible de s'abonner aux comptes d'autres sites supportant le protocole ActivityPub, comme PixelFed (équiv. Instagram) ou PeerTube (éq. YouTube) par exemple.

### Inconvénients

* Interface web moins jolie (mais interface mobile au même niveau voire mieux)
* Financement de l'hébergement : non-gratuit
* Pas de posts automatiques au changement de photos de profil (comme insta)
* Pas de rappels automatique des anniversaires (mais pourra être implémenté sur Nantral Platform)
* Pas de messagerie intégrée (Messenger pourra continuer à être utilisé dans un premier temps, puis remplacé par un autre service de messagerie)

## Public cible et périmètre de l'instance Mastodon

Deux possibilités s'offrent à nous pour l'ouverture d'une instance Mastodon dans l'école :
1. Une instance réservée aux étudiants : permet d'être plus libre dans les échanges, mais mets de côté le personnel, les enseignants-chercheurs et les doctorants de la vie de l'école.
2. Une instance plus ouverte, incluant personnels et enseignants : liberté de ton des étudiants plus restreinte, mais permet d'éviter des situations problématiques. À noter que les services de messegerie instantanée peuvent suffire pour que les étudiants aient un espace réservé. Permet aussi à au service Communication, à la Direction, à CNA ou au service Vie Étudiante de communiquer plus facilement et directement aux étudiants.

## Visibilité extérieure

Mastodon propose 2 modes de fonctionnement pour une instance :
* Mode **Fédération** : l'instance ECN serait fédérée avec toutes les autres instances du monde, c'est-à-dire qu'un post mis en ligne sur l'instance ECN serait aussi visible depuis toutes les autres instances du monde, et que n'importe quel post mis en ligne sur une instance serait aussi visible sur l'instance ECN. Il est possible de définir cependant une liste d'instances à exclure (qui contiendraient du contenu illicite par exemple). Un fil "Local" permet cependant de ne voir que les posts publiés sur l'instance ECN.
* Mode **Fermé** : l'instance ECN ne serait pas fédérée au réseau Mastodon, et vivrait donc en "isolement" : seuls les utilisateurs de l'instance ECN peuvent voir les posts publiés sur la même instance. Il est cependant possible de fédérer des instances supplémentaires (par exemple se fédérer à une hypothétique instance "Nantes Université")

À noter que pour une instance en mode "fédération", Mastodon ne permet pas lors de la publication d'un post de limiter la visibilité d'un post à l'instance émettrice uniquement (cf l'issue https://github.com/mastodon/mastodon/issues/861). Il existe cependant ceraines versions modifiées de Mastodon supportant la publication sur l'instance uniquement (par exemple https://github.com/hometown-fork/hometown).

## Support technique, financement et modération

Les contraintes de support techniques et motivations dépendant essentiellement du choix du périmètre retenu :
* dans le cas d'une instance réservée aux étudiants, le support technique devra être assuré uniquement par 3CN, le financement par le BDE, et la modération par les BDX et 3CN. Cela est assez ambitieux, dans la mesure où il est compliqué d'une part de trouver suffisamment de personnes qualifiées pour maintenir une instance vu le renouvellement annuel des étudiants, et d'autre part vu la contrainte budgétaire du BDE.
* dans le second cas d'une instance commune à l'échelle de l'école, le financement pourrait être assuré par l'école (potentiellement en partenariat avec le BDE), le support technique par la DSI (ou 3CN si la DSI manque de moyens humains, mais dans ce cas l'hébergement ne pourra se faire sur les serveurs de l'école), et la modération par les services Vie Étudiante, Communication et/ou Scolarité, avec potentiellement le BDE afin d'obtenir un équilibre des pouvoirs partagé.
