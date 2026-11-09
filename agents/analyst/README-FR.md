# Analyst

Fait parler les tableaux. Donnez à Analyst un export — ventes, factures, feuilles de temps,
réponses à une enquête, stock — et une question, même vague. Il vérifie ce que contient vraiment
le fichier, calcule chaque chiffre par des scripts, et vous remet une courte note : ce que montrent
les chiffres, ce qu'ils ne montrent pas, et le tableau et le graphique qui le prouvent.

## Pourquoi ses chiffres sont fiables

Un modèle de langage qui lit deux cents lignes et en annonce le total devine. Analyst ne le fait
jamais : chaque total, moyenne, décompte et pourcentage sort d'un script qui lit tout le fichier et
calcule exactement, au centime près. Le rôle du modèle est de poser les bonnes questions aux
données et de dire ce que signifient les réponses.

## Ce qu'il fait

- **Il lit** les fichiers CSV, TSV et Excel (.xlsx) ; il trouve le séparateur, la virgule
  décimale, le sens des dates.
- **Il vérifie d'abord** : cellules vides, texte parmi les nombres, lignes en double, valeurs
  écrites de plusieurs façons, dates ambiguës — et vous le dit avant de calculer.
- **Il calcule** : totaux, moyennes et médianes, décomptes, parts, par catégorie, par client, par
  mois, trimestre ou semaine, avec des filtres ; écarts et taux d'évolution.
- **Il dessine** des graphiques sobres — barres, barres horizontales, courbes — en fichiers SVG.
- **Il écrit la note** : la réponse d'abord, trois à cinq constats avec leurs chiffres, ce qui a
  été écarté, ce que l'on ne peut pas conclure. Sur demande, les résultats dans un fichier Excel.

## Ce qu'il lui faut

Un agent importé arrive sans autre droit que ceux par défaut. Sur sa page Agent :

| Réglage | Pourquoi |
|---|---|
| **Compétence : Analyse de données** | Sa méthode et ses scripts. Ils tournent dans un cadre fermé : Node seul, aucun réseau, lecture et écriture dans son propre dossier uniquement. Le premier lancement vous présente une carte ; vous pouvez approuver les scripts de cette compétence pour la session ou définitivement. |
| **Mémoire** (activée par défaut) | Pour retenir comment sont faits vos exports et vos définitions — jamais vos chiffres. |

Il n'a besoin ni d'accès système, ni du web, ni d'un service.

## Comment l'utiliser

1. **Joignez le fichier** à votre message (il doit être dans le dossier d'Analyst pour que les
   scripts le lisent) et posez votre question : « Voici les factures 2026 — quels sont nos dix
   meilleurs clients et quelle part du chiffre d'affaires représentent-ils ? »
2. Il vous dit ce qu'est le fichier et ce qui est douteux, et vous demande une fois ce qu'il ne
   peut pas savoir.
3. Vous recevez la note, avec les chemins des tableaux de résultats et des graphiques.

## Limites

Un tableau à la fois : il ne croise pas deux gros fichiers et ne construit pas de modèle
statistique. Les fichiers `.xls` et OpenDocument doivent d'abord être enregistrés en `.xlsx` ou en
`.csv`. Une formule d'un classeur donne le résultat que le fichier a gardé à son dernier
enregistrement.
