# MastoCN

Repository pour un projet de déploiement d'une instance Mastodon à Centrale Nantes.

## Quelle utilité ?

Mastodon permettrait de diminuer notre dépendance à Facebook dans les échanges numériques de la vie étudiante de l'école. En pratique, il s'intègre dans un plan plus global de transition vers des outils plus respectueux de la vie privée et plus sûrs :

| Besoin | Outil actuel | Proposition de remplacement |
| --- | --- | --- |
| Organisation d'évènements | Facebook | [Nantral Platform](https://nantral-platform.fr/) |
| Posts d'actus (annonce d'un évènement, questions, partages...) | Facebook | [Mastodon](https://piaille.fr/) |
| Communication "officielle" sur l'actu de l'école | E-mail | [Mastodon](https://piaille.fr/) |
| Messagerie instantanée | Messenger / Whatsapp | Pas encore défini. *Pistes : Signal / Télégram (+ sûrs), Zoom (outil officiel de l'école)* |
| Rappels d'anniversaire | Facebook | [Nantral Platform](https://nantral-platform.fr/) |
| Comm au format "story", vidéos courtes | Instagram | [PixelFed](https://github.com/pixelfed/pixelfed) |
| Groupes facebook des clubs et assos (type groupe 6-trouilles) | Groupe Facebook | [Mastodon](https://piaille.fr/) (abonnement à un compte) ou messagerie instantanée |
| Vidéos longues (CNT-CNC, captations de spectacles, trailers...) | YouTube | [PeerTube](https://www.peertube.fr/) |

Bien évidemment, ces transitions peuvent être faites indépendamment les unes des autres, en fonction des motivations des clubs et assos. À noter cependant que pour qu'elles soient effectives, elles nécessitent une volonté forte des BDX en charge, qui seuls ont la capacité d'effectuer une transition d'un service vers un autre.

À noter aussi que chaque service alternatif proposé repose sur l'auto-hébergement, ce qui peut entraîner des coûts non-négligeables (pour le BDE ou l'école suivant l'organisation hébergeante).

## Périmètre de l'instance Mastodon

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
