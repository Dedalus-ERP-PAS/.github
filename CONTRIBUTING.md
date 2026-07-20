# Contribuer

> Guide de contribution par défaut pour les dépôts de l'organisation
> **Dedalus-ERP-PAS**. Un dépôt peut fournir sa propre `CONTRIBUTING.md` (règles
> de build, branche cible, scopes) qui prime sur ce document.

Merci de contribuer à nos produits ! Ce guide décrit les conventions communes à
tous nos dépôts. Les spécificités (commandes de build, tests, branche cible)
sont documentées dans le `README` de chaque dépôt.

## Avant de commencer

- Discutez des changements importants dans une **issue** avant d'ouvrir une
  pull request, afin d'aligner l'approche.
- Vérifiez qu'une issue ou une PR ne traite pas déjà le sujet.
- Pour toute question de sécurité, suivez la [politique de sécurité](./SECURITY.md)
  — **n'ouvrez pas d'issue publique**.

## Branches

Format : `<numéro-issue>-<titre-en-kebab-case>`

- Commencer par le **numéro de l'issue** GitHub, suivi du titre en `kebab-case`.
- Tout en minuscules, mots séparés par des tirets, sans caractères spéciaux ni
  accents (`é → e`, `à → a`).

```
1367-onglet-maj-permettre-le-downgrade
```

Partez toujours d'une branche de base à jour et **ne poussez jamais directement**
sur `main`/`develop` — passez par une pull request.

## Commits — Conventional Commits (en français)

Format : `<type>(<scope>): <description à l'impératif> (#<issue>)`

| Type | Usage |
|---|---|
| `feat` | Nouvelle fonctionnalité |
| `fix` | Correction de bug |
| `docs` | Documentation uniquement |
| `refactor` | Restructuration sans changement fonctionnel |
| `perf` | Amélioration de performance |
| `test` | Ajout ou modification de tests |
| `style` | Formatage sans impact fonctionnel |
| `chore` | Maintenance, CI, dépendances |

Règles :

- **En français, à l'impératif** : « ajouter », « corriger », « permettre »… —
  pas de substantifs (« ajout de », « correction du »).
- Les commits `feat` et `fix` peuvent alimenter un **changelog lu par les
  clients** : rédigez-les pour un non-développeur, sans jargon ni noms de
  fichiers/fonctions. Le **scope y est obligatoire**.
- Le **numéro d'issue** est obligatoire sur le premier commit d'une branche.
- Un commit = un type. Ne mélangez pas `feat` et `fix`.

```bash
feat(console): permettre le retour à une version stable depuis une bêta (#1367)
fix(moteur): corriger la perte de messages HL7 lors d'une coupure réseau (#1289)
```

## Pull requests

- Ciblez la **branche d'intégration du dépôt** (souvent `develop`, jamais `main`
  sauf release) — voir le `README` du dépôt.
- Remplissez le **modèle de pull request**, en particulier le **rapport de test**
  qui prouve la résolution et permet le rejeu en non-régression.
- Si le dépôt utilise **Jira**, indiquez le ticket (ex. `HEX-666`) pour créer le
  lien automatique.
- Gardez la PR **focalisée** : un sujet par PR facilite la revue.
- Assurez-vous que la **CI passe** (build, lint, tests) avant de demander une
  revue.

## Style de code

Respectez le linter et le formateur configurés dans le dépôt. N'introduisez pas
d'outillage de formatage ad hoc ; utilisez les commandes fournies par le projet.

## Code de conduite

En participant, vous acceptez notre [code de conduite](./CODE_OF_CONDUCT.md).
