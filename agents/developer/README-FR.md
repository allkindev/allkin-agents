# Developer

Un développeur qui travaille comme Claude Code, dans Allkin : il explore le code avant d'y toucher,
planifie en quelques lignes, change aussi peu que la tâche le demande, vérifie en lançant les tests
et la compilation du projet, et rend compte sans détour — ce qui a changé, ce qui a été vérifié, ce
qui reste.

## Ce qu'il fait

- Il lit un projet comme le ferait un ingénieur qui le rejoint : comment il se construit et se
  teste, ses conventions, le code autour du changement.
- Il corrige des bogues (reproduire, localiser, corriger, prouver), ajoute des fonctionnalités, écrit
  des tests, refactorise quand on le lui demande, écrit des scripts, de la configuration, des
  migrations et de la documentation.
- Il lance les vérifications — tests, typage, lint, compilation — et lit leur résultat avant de dire
  qu'une chose est faite.
- Il relit du code avec la compétence **Revue de code** : des constats classés par gravité, chacun
  avec une ligne et un cas d'échec concret.
- Il garde git propre : il lit l'historique, ne committe que si vous le demandez, ne le réécrit
  jamais.

## Ce qu'il lui faut

Un agent importé arrive sans aucun droit. Developer travaille au mieux avec, sur sa page Agent :

| Réglage | Pourquoi |
|---|---|
| **Accès système : administrateur** (commandes) | Pour lancer les tests, la compilation, git, le gestionnaire de paquets. Chaque commande vous est d'abord montrée sur une carte ; vous pouvez en approuver une pour la session ou par un motif. |
| **Accès au web** | Pour lire la documentation d'une bibliothèque ou un message d'erreur que personne ne comprend. |
| **Sous-tâches** | Pour explorer un grand code en parallèle. |
| **Mémoire** (activée par défaut) | Pour retenir comment un projet se construit et les décisions que vous avez prises. |
| **Compétence : Revue de code** | Pour les relectures ; téléchargée quand vous la lui donnez. |

## Comment l'utiliser

1. Ouvrez une conversation avec Developer et réglez **le dossier de travail** (la pastille de la
   barre d'envoi) sur le projet : c'est là qu'arrivent ses fichiers et ses commandes.
2. Demandez le changement comme à un collègue : le bogue que vous voyez, la fonctionnalité que vous
   voulez, le fichier à relire. Il ne pose une question, par un formulaire, que si un vrai choix
   reste ouvert.
3. Lisez son compte rendu : le résultat d'abord, puis ce qui a changé et ce qui a été vérifié.

## Sécurité

Chaque commande passe par votre approbation. Developer ne télécharge jamais pour exécuter d'un seul
geste, ne désactive jamais une protection pour que quelque chose fonctionne, ne lance jamais une
commande destructrice — supprimer hors de son brouillon, vider une base, réécrire l'historique git —
sans votre instruction explicite et précise, et ne copie jamais un secret qu'il rencontre. Ce qu'il
n'a pas est un réglage d'Allkin ; il vous dit lequel.
