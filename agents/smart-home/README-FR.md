# Smart Home

L'administrateur de votre Home Assistant. Smart Home y fait ce que vous feriez dans son interface,
plus vite et avec plus de constance : il accueille les nouveaux périphériques avec vous, nomme
tout selon le schéma que vous avez choisi, écrit vos automatismes et construit vos tableaux de
bord — en lisant d'abord, en montrant ce qui va changer, et en gardant de quoi revenir en arrière.

## Ce qu'il fait

- **Nouveaux périphériques** : « écoutez les nouveaux périphériques » — il ouvre le réseau Zigbee
  (ZHA ou Zigbee2MQTT), Z-Wave ou RFXCOM, entend ce qui arrive, vous dit ce qu'est chaque
  périphérique et vous demande son nom, sa pièce et ce qu'il faut masquer. Puis il referme le
  réseau.
- **Noms** : il propose des schémas de nommage avec des exemples pris dans votre propre maison —
  `light.lustre_salon`, `binary_sensor.do_entree` — ou prend le vôtre, renomme en lot, et répare
  les automatismes et les tableaux de bord qui citaient les anciens identifiants.
- **Pièces, étages, étiquettes** : créés, rangés, chaque périphérique à sa place.
- **Automatismes, scripts, scènes, entrées** : vous dites « quand la porte d'entrée s'ouvre la
  nuit, allumez le couloir trois minutes » ; il reformule, vérifie chaque entité, valide, crée,
  puis teste avec votre accord.
- **Tableaux de bord** : par usage et par écran — un téléphone, une tablette murale —, en
  nouveaux tableaux de bord, jamais par-dessus les vôtres sans en garder la version précédente.
- **Le quotidien** : « éteignez le salon », « quelle température fait-il à l'étage ».
- **La santé** : ce que Home Assistant signale, les intégrations en erreur, les entités
  indisponibles, les piles faibles, les périphériques muets, les mises à jour en attente.

Il ne devine jamais un identifiant, ne laisse jamais un réseau ouvert, ne conserve aucun mot de
passe, et ne peut ni arrêter Home Assistant ni éteindre sa machine.

## Ce qu'il lui faut

Un agent importé arrive sans autre droit que ceux par défaut. Sur sa page Agent :

| Réglage | Pourquoi |
|---|---|
| **Services externes activés : Home Assistant** | Créez le service « Home Assistant » (page Services) avec l'adresse de votre installation et un jeton d'accès longue durée d'un administrateur (dans Home Assistant : votre profil → Sécurité → Jetons d'accès longue durée), testez-le, puis autorisez Smart Home à l'utiliser. Le jeton reste dans Allkin. |
| **Services externes en lecture seule** : désactivé | Activé, Smart Home ne peut que lire et écouter. |
| **Compétence : Administration de Home Assistant** | Sa méthode ; téléchargée quand vous la lui donnez. |
| **Peut planifier des actions** + compétence **Gérer les actions** | Pour un contrôle de santé hebdomadaire. Vous approuvez chaque action qu'il crée. |
| **Peut chercher et lire des pages sur le web** | Pour consulter la notice d'un appareil ou son geste d'appairage. Facultatif. |
| **Mémoire** (activée par défaut) | Pour retenir vos préférences. |

## Ce que vous verrez

Lire votre installation ne vous demande rien. **Chaque modification affiche une carte de
validation** dans la conversation — un renommage, une pièce, un tableau de bord enregistré, un
réseau ouvert —, une seule pour tout le lot, et vous pouvez approuver pour la session.
L'interrupteur **« Agir sans validation »** du service lève les cartes pour tous les agents, y
compris quand personne n'est là : laissez-le désactivé, sauf si vous voulez qu'une action modifie
votre installation toute seule.

## Comment l'utiliser

1. Créez le service Home Assistant et autorisez-le sur la page de Smart Home.
2. Dites : « Regardez mon installation. » Il en fait le tour, vous dit ce qu'il a trouvé et vous
   demande par quoi commencer.
3. Demandez ensuite avec vos mots : « écoutez les nouveaux périphériques Zigbee », « renommez
   proprement la cuisine », « faites un tableau de bord pour la tablette de l'entrée ».

## Limites

- Les fichiers écrits à la main en YAML (`configuration.yaml`, packages, tableaux de bord en mode
  YAML) sont hors de sa portée : il vous dit quoi y changer.
- Une intégration qui demande un compte ou un mot de passe, c'est vous qui l'ajoutez, dans Home
  Assistant.
- Il ne voit ni l'aspect d'un tableau de bord ni si une lampe s'est vraiment allumée : il vous le
  demande.
