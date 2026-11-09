# Orchestrator

Votre point d'entrée unique quand vous ne voulez pas chercher à quel agent vous adresser, ou quand
un travail en demande plusieurs. Orchestrator comprend la demande, la découpe s'il le faut, confie
chaque partie à l'agent le mieux placé, contrôle ce qui revient et vous donne une seule réponse.

## Ce qu'il fait

- Il choisit le bon agent pour une demande et la lui confie avec une consigne qui se suffit à
  elle-même : le but, la tâche, la matière, le résultat attendu.
- Il coordonne plusieurs agents sur un même travail, dans le bon ordre, en passant le résultat de
  l'un au suivant.
- Il lit chaque réponse en relecteur : un travail incomplet, contradictoire ou non vérifié repart
  une fois, puis vous est rapporté tel qu'il est.
- Il vous donne une seule réponse — le résultat d'abord, puis qui a fait quoi et ce qui reste —,
  jamais les réponses collées bout à bout.
- Il vous dit quand aucun agent ne convient, et quel modèle d'agent conviendrait.
- Il retient qui fait bien quoi et les préférences que vous lui avez données.

## Ce qu'il lui faut

Un agent importé arrive sans autre droit que ceux par défaut. Sur sa page Agent :

| Réglage | Pourquoi |
|---|---|
| **Peut communiquer avec les autres agents** (activé par défaut) | C'est tout son métier. Vous pouvez le limiter à une liste d'agents. |
| **Mémoire** (activée par défaut) | Pour apprendre qui fait bien quoi, et vos préférences. |

Il n'a besoin de rien d'autre : ni accès système, ni web. Plus vous avez d'agents spécialisés —
Writer, Researcher, Analyst, Developer… —, plus il est utile.

## Comment l'utiliser

1. Adressez-vous à Orchestrator comme à un assistant qui connaît toute l'équipe.
2. Pour un travail plus important, il vous donne son plan en quelques lignes avant de commencer.
3. Vous recevez une seule réponse, avec les chemins des fichiers produits.

## Bon à savoir

Un agent appelé par Orchestrator travaille sans personne devant lui : ce qui demanderait votre
approbation (une commande de la machine, une publication) peut y être refusé. Orchestrator vous dit
alors à quel agent vous adresser directement, avec la demande prête à coller. Il n'accorde jamais
un droit, ni à lui-même ni à un autre agent.
