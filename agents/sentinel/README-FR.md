# Sentinel

Veille sur vos serveurs. Sentinel fait sa ronde sur les machines que vous lui confiez, avec des
commandes qui ne modifient rien, compare avec le passage précédent, et vous dit ce qui demande
votre attention avant que cela ne devienne une panne : le disque qui se remplit, le certificat qui
expire dans dix jours, la sauvegarde arrêtée depuis trois semaines.

## Ce qu'il fait

- **Des rondes** : disque, mémoire et charge, services qui doivent tourner, mises à jour en
  attente et de sécurité, redémarrage requis, certificats, sauvegardes, connexions échouées et
  ports ouverts, erreurs dans les journaux.
- **Des tendances** : il garde les relevés de chaque ronde et vous dit où ils mènent — « `/var` à
  91 %, plein dans une dizaine de jours ».
- **Un rapport trié par urgence** : critique, alerte, note ; « rien à signaler » tient en une
  ligne. Chaque constat vient avec la commande exacte qu'il propose — qu'il ne lance que si vous
  le demandez.
- **Une fiche par machine** : ce qui doit y tourner, ce qui y est normal, vos seuils.
- **Les incidents** : quand quelque chose est en panne, un diagnostic pas à pas et un rapport
  écrit.
- **Tout seul** grâce aux Actions d'Allkin : une ronde chaque matin ou chaque semaine.

Il ne répare jamais de lui-même, n'éteint jamais une machine, ne lit jamais un secret.

## Ce qu'il lui faut

Un agent importé arrive sans autre droit que ceux par défaut. Sur sa page Agent :

| Réglage | Pourquoi |
|---|---|
| **Services : vos machines en SSH** | Créez un service « Machine en SSH » par serveur (page Services), testez-le, puis autorisez Sentinel à l'utiliser. Les identifiants restent dans Allkin. |
| **Accès au système : Lecture seule** | Pour vérifier la machine où tourne Allkin, en lecture seule, sans approbation. |
| **Peut planifier des actions** + compétence **Gérer les actions** | Pour des rondes régulières. Vous approuvez chaque action qu'il crée. |
| **Compétences : Contrôle de santé des serveurs, Rapport d'incident** | Ses méthodes ; téléchargées quand vous les lui donnez. |
| **Mémoire** (activée par défaut) | Pour retenir vos machines et vos seuils. |

### Des rondes sans vous

Chaque commande sur une machine en SSH vous présente une carte ; vous pouvez approuver pour la
session, ou enregistrer des motifs sur la page de Sentinel. Une ronde **lancée par une action**,
sans personne devant l'écran, ne s'exécute que sur les machines dont le service a l'interrupteur
**« Agir sans validation »** activé. Cet interrupteur laisse Sentinel y lancer des commandes
seul : ne l'activez que pour un **compte SSH qui ne peut que lire** sur cette machine (un
utilisateur ordinaire sans sudo, membre des groupes qui lisent les journaux).

## Comment l'utiliser

1. Créez les services SSH et autorisez-les sur la page de Sentinel.
2. Demandez : « Faites une première ronde. » Il découvre chaque machine, écrit sa fiche, et vous
   demande une fois ce qu'il ne peut pas observer : ce qui doit tourner, où vont les sauvegardes.
3. Acceptez l'action qu'il propose pour les rondes régulières, ou demandez « faites votre ronde »
   quand vous voulez.
4. Quand il signale quelque chose, décidez : il donne la commande ; vous dites oui ou vous la
   lancez vous-même.
