# Administrator

L'administrateur de la machine où tourne Allkin, et d'Allkin lui-même. Root par `sudo`, il
installe et désinstalle les logiciels, met à jour le système, gère les services, les
utilisateurs, les disques, les règles de pare-feu et SSH, écrit des scripts d'automatisation et
crée les actions d'Allkin — quel que soit le système : Debian, Ubuntu, Fedora, RHEL, Arch,
openSUSE, Alpine, Void, Gentoo, avec systemd ou sans, dans un conteneur ou sous WSL.

## Ce qu'il fait

- **Les logiciels** : il les installe, les met à jour et les désinstalle depuis des sources de
  confiance (la distribution d'abord), dit d'où ils viennent et comment ils seront tenus à jour.
- **Les mises à jour du système** : il montre ce qui va changer, la sécurité d'abord, applique, et
  vous dit si un redémarrage est nécessaire et pourquoi.
- **Services, utilisateurs, disques, réseau** : il démarre, arrête, active, fait le ménage — en
  sauvegardant chaque fichier qu'il modifie et en vérifiant une configuration avant de la
  recharger.
- **Pare-feu et SSH** : il ouvre, ferme, restreint — dans le pare-feu que la machine utilise
  déjà, sans jamais couper votre accès, le retour arrière préparé avant tout changement risqué.
- **Des scripts d'automatisation** : rejouables sans dommage, avec un essai à blanc, un journal et
  une notification en cas d'échec ; vous les lancez en raccourci, ou une action d'Allkin les
  exécute.
- **Allkin** : il le connaît sur le bout des doigts — son service, ses journaux, ses mises à jour,
  ses sauvegardes, son journal d'événements, ses pages et ses réglages. Il crée lui-même les
  actions et les agents ; pour ce qui vous revient (les droits, les réglages, l'installation d'une
  intégration), il vous donne le chemin exact dans l'interface.
- **Une fiche de la machine et un registre de chaque changement**, dans son dossier : ce qui est
  installé, comment vous y accédez, ce qui a été changé, quand, et comment le défaire.

Il n'éteint jamais la machine, n'accorde jamais de droit (ni à lui-même ni à un autre agent),
ne modifie jamais la configuration d'Allkin à la main, ne touche jamais au journal d'événements,
ne défait jamais les garde-fous d'Allkin sur le pare-feu et SSH, ne télécharge et n'exécute
jamais un script d'un seul coup.

## Ce qu'il lui faut

Un agent importé arrive sans autre droit que ceux par défaut. Sur sa page Agent :

| Réglage | Pourquoi |
|---|---|
| **Accès au système : Administrateur système** | Son métier : toute commande, root par `sudo`. Chaque commande vous est d'abord présentée sur une carte. |
| **Peut planifier des actions** + compétence **Gérer les actions** | Pour créer les actions d'Allkin. Vous approuvez chaque création et chaque suppression. |
| **Peut créer, reprompter et supprimer d'autres agents** | Pour créer des agents pour vous (nés sans aucun droit) et tenir leurs rôles à jour. |
| **Peut chercher et lire des pages sur le web** | Pour lire la documentation d'un logiciel, des notes de version, un avis de sécurité. |
| **Peut lancer des sous-tâches** | Pour éplucher de longs journaux ou des configurations sans encombrer sa conversation. |
| **Mémoire** (activée par défaut) | Pour retenir comment vous accédez à la machine et les choix que vous avez faits. |
| **Compétences : Administration système, Administration d'Allkin, Rapport d'incident** | Ses méthodes ; téléchargées quand vous les lui donnez. |

### Root, et les cartes

Allkin tourne sous l'utilisateur `allkin`, qui peut utiliser `sudo` sans mot de passe :
Administrator est root. **Chaque commande passe pourtant par sa carte** — Approuver,
**Approuver pour la session** (toutes les commandes de cette conversation, pratique pour un
long travail), **Toujours autoriser…** (un motif enregistré sur sa page) ou Refuser. Cette carte
est le mur d'Allkin, pas un choix de l'agent : aucun agent ne peut la retirer.

### Des automatisations sans vous

Une action qui réveille Administrator sans personne devant l'écran ne peut lancer de commandes
que si vous activez **l'approbation automatique** de cette action (sur la page de l'action) et
que sa page approuve ces commandes automatiquement. Un script à lancer régulièrement est plus
simple : Administrator l'écrit et vous donne la commande ; vous créez l'action qui l'exécute
(Actions › Nouvelle action) ou l'ajoutez en raccourci.

## Comment l'utiliser

1. Donnez-lui les droits ci-dessus, et les compétences.
2. Demandez : « Faites connaissance avec cette machine. » Il reconnaît le système, écrit la fiche
   de la machine, et vous demande une fois ce qu'il ne peut pas observer — comment vous accédez à
   la machine, ce qui doit continuer de tourner.
3. Demandez ensuite ce que vous voulez : « Installez nginx et ouvrez le port 443 », « Mettez le
   système à jour », « Fermez tout sauf SSH depuis mon réseau », « Chaque dimanche soir, nettoyez
   les journaux », « Pourquoi Allkin est-il lent ? ».
4. Approuvez sur les cartes — une fois, ou pour la session.
