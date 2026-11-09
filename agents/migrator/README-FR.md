# Migrator

Un agent qui fait venir dans Allkin vos agents d'**OpenClaw** (ex-Clawdbot, Moltbot) ou de
**NanoClaw**. Donnez-lui un zip de votre ancienne installation : il laisse les secrets de côté,
réécrit pour Allkin le rôle et la mémoire de chaque agent, convertit ses compétences, et vous
remet une archive par agent à importer, avec une courte liste de ce qui reste à faire.

Le but est une bonne migration, pas une copie parfaite : ce qui trouve simplement sa place dans
Allkin est repris, le reste vous est listé.

## Ce qu'il fait

- Il reconnaît une installation OpenClaw ou NanoClaw (les deux organisations de NanoClaw) et liste
  ce qu'elle contient : agents, rôles, mémoires, notes, compétences, tâches planifiées, canaux.
- Il vous demande, par un seul formulaire, ce qu'il faut migrer.
- Il écrit un rôle par agent à partir de son identité, de son âme et de ses règles ; il garde ses
  faits durables en mémoire et ses notes en fichiers.
- Il convertit les compétences dans un dépôt que vous ajoutez dans les Paramètres ; les scripts
  qui ne peuvent pas tourner dans Allkin sont mis de côté, avec la raison.
- Il liste les actions à créer, les services et canaux à connecter, les droits à accorder.

## Ce qu'il lui faut

| Réglage | Pourquoi |
|---|---|
| **Compétence : Migrer des agents** | Toute sa méthode et ses scripts ; téléchargée à la création de l'agent. |
| **Mémoire** (activée par défaut) | Pour retenir ce qu'il a migré. |

Rien d'autre : il travaille dans son propre dossier. Si vous lui donnez le droit « Peut
planifier des actions » et la compétence « Gérer les actions », il peut aussi créer lui-même les
actions, chacune approuvée par vous.

## Comment l'utiliser

1. Sur l'ancienne machine, faites un zip de l'installation :
   - OpenClaw : `cd ~ && zip -r openclaw.zip .openclaw -x '.openclaw/agents/*/sessions/*' '*/node_modules/*'`
   - NanoClaw : `zip -r nanoclaw.zip nanoclaw -x '*/node_modules/*' 'nanoclaw/data/sessions/*'`
2. Ouvrez une conversation avec Migrator, joignez le zip, demandez-lui la migration.
3. Répondez à son formulaire, puis suivez sa liste : importez chaque archive (le « + » de la
   liste des agents › Importer un agent), ajoutez le dépôt de compétences, accordez les droits,
   connectez les services.

## Sécurité

Les identifiants, les transcriptions et les valeurs du `.env` ne sont jamais extraits ; chaque
jeton ou clé de la configuration est remplacé ; une archive est refusée tant qu'il reste quelque
chose qui ressemble à un secret. Le code de l'ancienne plateforme est lu, jamais exécuté. Chaque
agent importé arrive sans aucun droit et passe par la carte d'identité et son bouton Vérifier,
comme tout import. Supprimez le zip du dossier `Upload/` de l'agent une fois la migration
terminée.
